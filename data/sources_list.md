# Data Sources List

## Overview

This document provides detailed information about the data sources used in the AxiomHive US Manufacturing Intelligence project. All data is sourced from publicly available, authoritative sources to ensure transparency, reproducibility, and credibility.

## Data Files in This Repository

### 1. latest_ISM_release.csv

**Description**: Institute for Supply Management (ISM) Manufacturing PMI data

**Time Period**: January 2024 - April 2025

**Update Frequency**: Monthly

**Columns**:
- `Date`: First day of the month (YYYY-MM-DD format)
- `PMI`: Overall Purchasing Managers' Index
- `New_Orders`: New Orders sub-index
- `Production`: Production sub-index
- `Employment`: Employment sub-index
- `Supplier_Deliveries`: Supplier Deliveries sub-index
- `Inventories`: Inventories sub-index
- `Customers_Inventories`: Customers' Inventories sub-index
- `Prices`: Prices sub-index
- `Backlog_Orders`: Backlog of Orders sub-index
- `New_Export_Orders`: New Export Orders sub-index
- `Imports`: Imports sub-index

**Source Information**:
- **Organization**: Institute for Supply Management (ISM)
- **Dataset**: Manufacturing ISM Report On Business®
- **Primary URL**: https://www.ismworld.org/supply-management-news-and-reports/reports/ism-report-on-business/pmi/
- **Data Portal**: https://www.ismworld.org/
- **Access Type**: Public (published monthly in press releases)
- **License**: Publicly available data from ISM press releases

**Methodology**: 
The ISM Manufacturing PMI is a composite index based on surveys of purchasing and supply executives across various manufacturing industries. A reading above 50 indicates expansion, while below 50 indicates contraction.

**Citation**:
```
Institute for Supply Management. "Manufacturing ISM Report On Business®". 
Monthly releases, January 2024 - April 2025. 
Retrieved from https://www.ismworld.org/
```

**Notes**:
- Data values are index values (0-100 scale)
- Historical data available dating back to 1948
- Considered a leading economic indicator
- Released on the first business day of each month

### 2. s_and_p_manufacturing.csv

**Description**: S&P Global US Manufacturing PMI data

**Time Period**: January 2024 - April 2025

**Update Frequency**: Monthly

**Columns**:
- `Date`: First day of the month (YYYY-MM-DD format)
- `PMI`: Overall Purchasing Managers' Index
- `Output`: Output/Production sub-index
- `New_Orders`: New Orders sub-index
- `Employment`: Employment sub-index
- `Input_Prices`: Input Prices sub-index
- `Output_Prices`: Output Prices/Selling Prices sub-index
- `Future_Output`: Future Output Expectations sub-index
- `Quantity_Purchased`: Quantity of Purchases sub-index
- `Suppliers_Delivery_Times`: Suppliers' Delivery Times sub-index
- `Stocks_Purchases`: Stocks of Purchases sub-index
- `Stocks_Finished_Goods`: Stocks of Finished Goods sub-index

**Source Information**:
- **Organization**: S&P Global (formerly IHS Markit)
- **Dataset**: S&P Global US Manufacturing PMI®
- **Primary URL**: https://www.pmi.spglobal.com/Public/Home/PressRelease/
- **Data Portal**: https://www.spglobal.com/marketintelligence/en/mi/products/pmi.html
- **Access Type**: Public (headline data published in monthly press releases)
- **License**: Publicly available headline data from S&P Global press releases

**Methodology**: 
Based on survey responses from purchasing managers at around 400 manufacturing companies. Survey responses reflect the change, if any, in the current month compared to the previous month. A reading above 50 indicates expansion, below 50 indicates contraction.

**Citation**:
```
S&P Global. "S&P Global US Manufacturing PMI®". 
Monthly releases, January 2024 - April 2025. 
Retrieved from https://www.pmi.spglobal.com/
```

**Notes**:
- Data values are diffusion indices (0-100 scale)
- Survey conducted mid-month, released early in following month
- Part of the global PMI survey series covering 40+ economies
- Flash estimates available approximately one week before final data

## Additional Public Data Sources

### Federal Reserve Economic Data (FRED)

**Organization**: Federal Reserve Bank of St. Louis

**Relevant Datasets**:
- Industrial Production: Manufacturing (IPMAN)
- Capacity Utilization: Manufacturing (CUMFNS)
- Manufacturers' New Orders (AMTMNO)
- Manufacturing and Trade Inventories (BUSINV)

**Access**:
- **Website**: https://fred.stlouisfed.org/
- **API**: https://fred.stlouisfed.org/docs/api/
- **License**: Public Domain (U.S. Government data)

**Citation Format**:
```
U.S. Board of Governors of the Federal Reserve System (US), [Series Name], 
retrieved from FRED, Federal Reserve Bank of St. Louis; 
https://fred.stlouisfed.org/series/[SERIES_ID], [Access Date]
```

### U.S. Census Bureau

**Organization**: U.S. Census Bureau

**Relevant Datasets**:
- Manufacturers' Shipments, Inventories, and Orders (M3)
- Current Industrial Reports
- Annual Survey of Manufactures

**Access**:
- **Website**: https://www.census.gov/manufacturing/
- **Data Portal**: https://www.census.gov/econ/currentdata/
- **API**: https://www.census.gov/data/developers/data-sets.html
- **License**: Public Domain (U.S. Government data)

**Citation Format**:
```
U.S. Census Bureau. [Dataset Name]. 
Washington, D.C.: U.S. Census Bureau. 
Available at: [URL], [Access Date]
```

### Bureau of Labor Statistics (BLS)

**Organization**: U.S. Bureau of Labor Statistics

**Relevant Datasets**:
- Employment, Hours, and Earnings (Manufacturing)
- Producer Price Index - Commodities
- Productivity and Costs - Manufacturing
- Industry Employment Projections

**Access**:
- **Website**: https://www.bls.gov/
- **Data Tools**: https://data.bls.gov/
- **API**: https://www.bls.gov/developers/
- **License**: Public Domain (U.S. Government data)

**Citation Format**:
```
U.S. Bureau of Labor Statistics. [Series Title]. 
[Publication]. Retrieved [Access Date] from https://www.bls.gov/
```

## Data Provenance

### Data Collection Process

1. **Identification**: Identify authoritative public data sources for US manufacturing indicators
2. **Verification**: Verify source credibility and data quality
3. **Acquisition**: Download/retrieve data from official sources
4. **Documentation**: Record acquisition timestamp, source URL, and methodology
5. **Validation**: Verify data integrity and completeness
6. **Storage**: Store raw data with full metadata in version control

### Data Quality Assurance

- **Source Verification**: All sources are well-established, authoritative organizations
- **Cross-Validation**: Compare data across multiple sources when available
- **Temporal Consistency**: Verify logical consistency across time periods
- **Range Checks**: Ensure values fall within expected ranges
- **Completeness**: Check for missing values and document gaps

### Data Update Schedule

- **ISM PMI**: Updated monthly on the first business day of each month
- **S&P Global PMI**: Updated monthly, typically mid-month
- **FRED Data**: Varies by series (monthly, quarterly, or annual)
- **Census Data**: Varies by dataset (monthly, quarterly, or annual)
- **BLS Data**: Varies by series (monthly, quarterly, or annual)

## Data Usage Guidelines

### Attribution Requirements

1. **Always cite the original source** when using this data
2. **Include access date** to enable reproducibility
3. **Reference methodology** from source documentation
4. **Maintain source links** in all derivatives

### Limitations and Considerations

- **Revisions**: Economic data is often revised after initial release
- **Seasonality**: Some series are seasonally adjusted, others are not
- **Methodology Changes**: Survey methodologies may change over time
- **Coverage**: PMI surveys cover purchasing managers, not all manufacturers
- **Timing**: Different sources release data on different schedules

### Best Practices

1. **Always use the most recent data** available from sources
2. **Document any transformations** applied to raw data
3. **Preserve raw data** in original format
4. **Track data versions** with timestamps and hashes
5. **Maintain audit trail** of all data processing steps

## Contact and Support

### For Questions About This Repository

- **GitHub Issues**: https://github.com/axiom-hive/AxiomHive-USManufacturing-Intelligence/issues
- **GitHub Discussions**: https://github.com/axiom-hive/AxiomHive-USManufacturing-Intelligence/discussions

### For Questions About Original Data Sources

- **ISM**: Contact ISM directly at https://www.ismworld.org/about-us/contact-us/
- **S&P Global**: Contact S&P Global at https://www.spglobal.com/en/contact-us/
- **FRED**: fred@stls.frb.org
- **Census**: https://ask.census.gov/
- **BLS**: blsdata_staff@bls.gov

## Version History

- **Version 1.0** (2024-01-15): Initial release with ISM and S&P Global PMI data
- **Data Coverage**: January 2024 - April 2025
- **Next Update**: May 2025 (scheduled)

## License and Terms of Use

This repository contains data compiled from publicly available sources. Each data source has its own terms of use:

- **ISM Data**: Subject to ISM's terms of use for publicly released data
- **S&P Global Data**: Subject to S&P Global's terms for publicly released headline data
- **U.S. Government Data** (FRED, Census, BLS): Public Domain

Users should:
- Review and comply with original source terms of use
- Provide appropriate attribution to original sources
- Not misrepresent the provenance of the data
- Acknowledge that data is provided "as is" without warranty

## Acknowledgments

We acknowledge and thank the following organizations for making their data publicly available:

- Institute for Supply Management (ISM)
- S&P Global
- Federal Reserve Bank of St. Louis (FRED)
- U.S. Census Bureau
- U.S. Bureau of Labor Statistics

Their commitment to data transparency enables economic research and informed decision-making.
