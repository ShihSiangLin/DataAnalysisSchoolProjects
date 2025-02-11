# Housing Smurfs: Apartment Analytics Platform

See [final report](./final_report.pdf) for references.
## Data Architecture

### Data Sources
#### Web Scraping Endpoints
- **Google Reviews**: Review metrics and user feedback
- **Yelp**: Apartment listings and ratings
- **Apartments.com**: Property details and amenities
- **ApartmentRatings**: Tenant reviews and responses

#### Primary Data Collection
- **Survey Implementation**: Google Forms
- **Target Demographic**: UMD students
- **Data Focus**: Lease information and tenant preferences

## Technical Implementation

### Database Schema
```sql
-- Implementation in Microsoft SQL Server Management Studio
-- Connected to RHSmith SQL Server
-- Reference: Project_0507_DDL.sql