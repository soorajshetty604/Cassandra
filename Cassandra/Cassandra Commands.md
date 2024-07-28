SELECT * FROM `<key space>`.`<table>`;
USE `<keyspace>`;

INSERT into `<tablename>`(column1, column2) VALUES( value1, value2);
COPY `<tablename>`(column1, column2) FROM '/home/path/to/file' WITH HEADERS = true;

DESCRIBE TABLES; 

**Partitions:**

SELECT token(video_id), video_id
FROM videos;

CREATE TABLE video_metadata (
    tag text,
    video_id timeuuid,
    added_date timestamp,
    title text,
    PRIMARY KEY (tag, video_id)
);
// will create the table with the partition keys, table will be partitoned by the tag


COPY video_metadata (tag , video_id , added_date , title ) FROM '/workspace/ds201-lab01/data-files/videos-by-tag.csv' WITH HEADER = true ;

DROP TABLE videos_by_tag;