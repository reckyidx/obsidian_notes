#### Advanace Topics

##### 1. Object Relationship Mapping (ORM)

	Map between object in programming and table in relationship database
		 Pros: CRUD interaction without SQl, Migration, Association (1-1, 1-many,                many- many), lazy loading(load data when needed), Transaction                     support, Query builders)
		 

## PostgreSQL Index Types

PostgreSQL offers the most variety of index types:

### 1. **B-tree** (Default)

```sql
CREATE INDEX idx_name ON employee(name);
CREATE INDEX idx_name_age ON employee(name, age);
```

- **Use for:** Equality, range queries (`<`, `>`, `BETWEEN`), sorting
- **Best for:** High cardinality columns
- **Supports:** `=`, `<`, `<=`, `>`, `>=`, `BETWEEN`, `IN`, `IS NULL`, `ORDER BY`

### 2. **Hash**

```sql
CREATE INDEX idx_name_hash ON employee USING HASH(name);
```

- **Use for:** Simple equality comparisons only
- **Supports:** Only `=` operator
- **Note:** Rarely used; B-tree is usually better

### 3. **GiST (Generalized Search Tree)**

```sql
CREATE INDEX idx_location ON places USING GIST(location);
CREATE INDEX idx_text_search ON articles USING GIST(to_tsvector('english', content));
```

- **Use for:** Geometric data, full-text search, range types
- **Best for:** Complex data types, custom operators

### 4. **GIN (Generalized Inverted Index)**

```sql
CREATE INDEX idx_tags ON products USING GIN(tags);
CREATE INDEX idx_fulltext ON articles USING GIN(to_tsvector('english', content));
CREATE INDEX idx_jsonb ON data USING GIN(json_column);
```

- **Use for:** Arrays, JSONB, full-text search, multiple values per row
- **Best for:** Containment queries (`@>`, `<@`, `?`, etc.)

### 5. **BRIN (Block Range Index)**

```sql
CREATE INDEX idx_created_at ON logs USING BRIN(created_at);
```

- **Use for:** Very large tables with naturally ordered data
- **Best for:** Time-series data, append-only tables
- **Advantage:** Extremely small index size

### 6. **SP-GiST (Space-Partitioned GiST)**

```sql
CREATE INDEX idx_phone ON contacts USING SPGIST(phone_number);
CREATE INDEX idx_ip ON network_logs USING SPGIST(ip_address);
```

- **Use for:** Non-balanced data structures, prefix searches
- **Best for:** Phone numbers, IP addresses, geographic data

### 7. **Bloom Filter** (Extension)

```sql
CREATE EXTENSION bloom;
CREATE INDEX idx_bloom ON employee USING BLOOM(name, age, gender);
```

- **Use for:** Multiple column queries where only some columns are used
- **Best for:** Testing membership, reducing false positives

## Special Index Features in PostgreSQL

### Partial Index

```sql
CREATE INDEX idx_active_employees ON employee(name) 
WHERE status = 'active';
```

- Index only rows matching a condition

### Expression Index

```sql
CREATE INDEX idx_lower_name ON employee(LOWER(name));
CREATE INDEX idx_year ON orders(EXTRACT(YEAR FROM order_date));
```

- Index computed values

### Covering Index (INCLUDE)

```sql
CREATE INDEX idx_name_covering ON employee(name) INCLUDE (age, gender);
```

- Include extra columns for index-only scans

### Unique Index

```sql
CREATE UNIQUE INDEX idx_email_unique ON employee(email);
```

- Enforce uniqueness

### Concurrent Index Creation

```sql
CREATE INDEX CONCURRENTLY idx_name ON employee(name);
```

- Create index without blocking writes

## Other SQL Databases

### MySQL/MariaDB

```sql
-- B-tree (default)
CREATE INDEX idx_name ON employee(name);

-- Full-text
CREATE FULLTEXT INDEX idx_description ON products(description);

-- Spatial (for geometry data)
CREATE SPATIAL INDEX idx_location ON places(coordinates);

-- Hash (Memory/NDB engine only)
CREATE INDEX idx_name USING HASH ON employee(name);
```

### SQL Server

```sql
-- Clustered Index (only one per table, defines physical order)
CREATE CLUSTERED INDEX idx_id ON employee(id);

-- Non-clustered Index (B-tree)
CREATE NONCLUSTERED INDEX idx_name ON employee(name);

-- Columnstore Index (for analytics)
CREATE COLUMNSTORE INDEX idx_columnstore ON sales(product_id, amount, date);

-- Full-text Index
CREATE FULLTEXT INDEX ON articles(content);

-- Spatial Index
CREATE SPATIAL INDEX idx_location ON places(coordinates);

-- XML Index
CREATE PRIMARY XML INDEX idx_xml ON documents(xml_data);

-- Filtered Index (like PostgreSQL partial)
CREATE INDEX idx_active ON employee(name) WHERE status = 'active';
```

### Oracle

```sql
-- B-tree (default)
CREATE INDEX idx_name ON employee(name);

-- Bitmap Index (for low cardinality)
CREATE BITMAP INDEX idx_gender ON employee(gender);

-- Function-based Index
CREATE INDEX idx_upper_name ON employee(UPPER(name));

-- Text/Domain Index
CREATE INDEX idx_text ON documents(content) 
INDEXTYPE IS CTXSYS.CONTEXT;

-- Spatial Index
CREATE INDEX idx_spatial ON locations(geometry) 
INDEXTYPE IS MDSYS.SPATIAL_INDEX;
```

### SQLite

```sql
-- B-tree (only type available)
CREATE INDEX idx_name ON employee(name);

-- Unique Index
CREATE UNIQUE INDEX idx_email ON employee(email);
```

## Quick Reference: When to Use Which

|Index Type|Best Use Case|
|---|---|
|**B-tree**|General purpose, ranges, sorting|
|**Hash**|Simple equality (rarely used)|
|**GIN**|Arrays, JSONB, full-text search|
|**GiST**|Geometric data, custom types|
|**BRIN**|Very large time-series tables|
|**Bitmap**|Low cardinality columns (Oracle)|
|**Columnstore**|Analytics/OLAP (SQL Server)|
|**Full-text**|Text search across databases|

**PostgreSQL is the most feature-rich** when it comes to index types, which is one reason it's popular for complex applications!