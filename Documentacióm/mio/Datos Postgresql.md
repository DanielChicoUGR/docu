 **name** | **aliases** | **description** 
---|---|---
 bigint | int8 | signed eight-byte integer 
 bigserial | serial8 | autoincrementing eight-byte integer 
 bit [ (n) ] | &nbsp; | fixed-length bit string 
 bit varying [ (n) ] | varbit [ (n) ] | variable-length bit string 
 boolean | bool | logical boolean (true/false) 
 box | &nbsp; | rectangular box on a plane 
 bytea | &nbsp; | binary data (“byte array”) 
 character [ (n) ] | char [ (n) ] | fixed-length character string 
 character varying [ (n) ] | varchar [ (n) ] | variable-length character string 
 cidr | &nbsp; | ipv4 or ipv6 network address 
 circle | &nbsp; | circle on a plane 
 date | &nbsp; | calendar date (year, month, day) 
 double precision | float8 | double precision floating-point number (8 bytes) 
 inet | &nbsp; | ipv4 or ipv6 host address 
 integer | int, int4 | signed four-byte integer 
 interval [ fields ] [ (p) ] | &nbsp; | time span 
 json | &nbsp; | textual json data 
 jsonb | &nbsp; | binary json data, decomposed 
 line | &nbsp; | infinite line on a plane 
 lseg | &nbsp; | line segment on a plane 
 macaddr | &nbsp; | mac (media access control) address 
 macaddr8 | &nbsp; | mac (media access control) address (eui-64 format) 
 money | &nbsp; | currency amount 
 numeric [ (p, s) ] | decimal [ (p, s) ] | exact numeric of selectable precision 
 path | &nbsp; | geometric path on a plane 
 pg_lsn | &nbsp; | postgresql log sequence number 
 pg_snapshot | &nbsp; | user-level transaction id snapshot 
 point | &nbsp; | geometric point on a plane 
 polygon | &nbsp; | closed geometric path on a plane 
 real | float4 | single precision floating-point number (4 bytes) 
 smallint | int2 | signed two-byte integer 
 smallserial | serial2 | autoincrementing two-byte integer 
 serial | serial4 | autoincrementing four-byte integer 
 text | &nbsp; | variable-length character string 
 time [ (p) ] [ without time zone ] | &nbsp; | time of day (no time zone) 
 time [ (p) ] with time zone | timetz | time of day, including time zone 
 timestamp [ (p) ] [ without time zone ] | &nbsp; | date and time (no time zone) 
 timestamp [ (p) ] with time zone | timestamptz | date and time, including time zone 
 tsquery | &nbsp; | text search query 
 tsvector | &nbsp; | text search document 
 txid_snapshot | &nbsp; | user-level transaction id snapshot (deprecated; see pg_snapshot) 
 uuid | &nbsp; | universally unique identifier 
 xml | &nbsp; | xml data 

