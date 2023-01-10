# Initial requirements

- [ ] download MOMA dataset: https://media.githubusercontent.com/media/MuseumofModernArt/collection/master/Artists.csv
- [ ] create a table in postgresql that maps the columns of the MOMA dataset

```sql
CREATE TABLE artists (
  ConstituentID SERIAL,
  DisplayName VARCHAR(50),
  Nationality VARCHAR(50),
  Gender VARCHAR(50),
  BeginDate DATE,
  EndDate DATE, 
  Wiki VARCHAR(50),
  QID VARCHAR(255),
  ULAN
  PRIMARY KEY (ConstituentID)
)
```

- Run command in psql 
```sql 
COPY artists (ConstituentID,DisplayName,ArtistBio,Nationality,Gender,BeginDate,EndDate,Wiki QID,ULAN)
FROM '<filepath>\moma.csv'
DELIMITER ','
CSV HEADER;
```