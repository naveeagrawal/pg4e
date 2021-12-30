-- Assignment 3 Musical Track Database plus Artists
CREATE TABLE album(
    id SERIAL,
    title VARCHAR(128) UNIQUE,
    PRIMARY KEY(id)
);

CREATE TABLE track(
    id SERIAL,
    title TEXT,
    artist TEXT,
    album TEXT,
    album_id INTEGER REFERENCES album(id) ON DELETE CASCADE,
    count INTEGER,
    rating INTEGER,
    len INTEGER,
    PRIMARY KEY(id)
);

CREATE TABLE artist(
    id SERIAL,
    name VARCHAR(128) UNIQUE,
    PRIMARY KEY(id)
);

CREATE TABLE tracktoartist(
    id SERIAL,
    track VARCHAR(128),
    
