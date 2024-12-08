# SQL Music Company Database

## Project Overview
This project involves the creation of a relational database system for managing a music library. It contains tables for **bands**, **albums**, and **songs**, with their relationships defined using foreign keys. The database is designed to store data about music bands, their albums, and the songs within those albums. The project demonstrates a comprehensive approach to relational database design and implementation using SQL.

## Database Structure

### 1. **Database Name**: `record_company`
The database is created with the name `record_company`.

### 2. **Tables**
- **`bands`**:
  - Columns:
    - `id` (Primary Key): Auto-incremented integer to uniquely identify each band.
    - `name`: The name of the band.

- **`albums`**:
  - Columns:
    - `id` (Primary Key): Auto-incremented integer to uniquely identify each album.
    - `name`: The name of the album.
    - `release_year`: The year the album was released.
    - `band_id` (Foreign Key): Links the album to the corresponding band in the `bands` table.

- **`songs`**:
  - Columns:
    - `id` (Primary Key): Auto-incremented integer to uniquely identify each song.
    - `name`: The name of the song.
    - `length`: The duration of the song in minutes.
    - `album_id` (Foreign Key): Links the song to the corresponding album in the `albums` table.

## Features
- Properly normalized relational database design.
- Referential integrity ensured via foreign key constraints.
- Comprehensive dataset representing multiple bands, albums, and songs.
- Modular and expandable design, allowing additional tables and relationships to be added as needed.

## Data Details
### Bands
This table contains the names of popular music bands such as "Seventh Wonder", "Metallica", and "Within Temptation".

### Albums
Each album record is linked to a band and includes details like the album name and release year. For example, "Master of Puppets" is an album by "Metallica".

### Songs
Each song record is linked to an album and includes details like the song name and duration. For example, "Master of Puppets" (the song) belongs to the album "Master of Puppets" and has a duration of 8 minutes and 35 seconds.

## Usage Instructions
1. **Database Setup**:
   - Create the database by running:
     ```sql
     CREATE DATABASE record_company;
     USE record_company;
     ```

2. **Create Tables**:
   - Execute the provided SQL statements to create the `bands`, `albums`, and `songs` tables.

3. **Insert Data**:
   - Populate the tables with the provided SQL `INSERT` statements.

4. **Query Examples**:
   - Find all albums by a specific band:
     ```sql
     SELECT albums.name, albums.release_year
     FROM albums
     JOIN bands ON albums.band_id = bands.id
     WHERE bands.name = 'Metallica';
     ```
   - List all songs in a specific album:
     ```sql
     SELECT songs.name, songs.length
     FROM songs
     JOIN albums ON songs.album_id = albums.id
     WHERE albums.name = 'Tiara';
     ```
   - Retrieve all bands and their albums:
     ```sql
     SELECT bands.name AS Band, albums.name AS Album
     FROM bands
     JOIN albums ON bands.id = albums.band_id;
     ```

## Project Goals
- Showcase the ability to design and implement relational databases.
- Understand how to create relationships between tables using foreign keys.
- Practice SQL queries to retrieve, filter, and manipulate data.

## Future Enhancements
- Add a **genres** table to categorize bands or albums.
- Include a **ratings** table for user reviews and ratings of albums or songs.
- Implement advanced SQL features such as triggers or stored procedures for data automation.

## Technologies Used
- SQL (Structured Query Language)

## Author
This project was developed as part of a database design learning exercise. For any queries or feedback, feel free to reach out.
