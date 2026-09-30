## Compute-Aware Table-Scanning

This is the implementation of paper "Compute-Aware Table-scanning for Analytical Databases" (under review) based on [DuckDB(v1.3)](https://github.com/duckdb/duckdb). Should you have any question with the code, contact the author via zhouyang.xie@unsw.edu.au or leave an issue.

### Building and Running

Consult the [official document](https://duckdb.org/docs/1.3/dev/building/overview) of DuckDB(v1.3) to build from source.

The SQL interface is the same as DuckDB. Consult [here](https://duckdb.org/docs/1.3/sql/introduction).

### Implementation

Our method is integrated into the Parquet table scan operator of DuckDB. Find the core implementation in:

* Zone-based Table-scanning:
  * `extension/parquet/parquet_reader.cpp`
  * `extension/parquet/zoned_selection_vector.cpp`
  * `extension/parquet/zone_manager.cpp`
* ZBF: `extension/parquet/include/zbf.hpp`
* The modified Parquet format prototype: `dev-dynscan/third_party/parquet/parquet.thrift`
