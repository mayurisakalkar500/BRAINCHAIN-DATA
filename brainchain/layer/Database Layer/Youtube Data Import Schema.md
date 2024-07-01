CREATE TABLE Users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    youtube_id VARCHAR(255) UNIQUE NOT NULL,
    username VARCHAR(255),
    email VARCHAR(255),
    profile_url VARCHAR(255),
    join_date DATE
);

CREATE TABLE Videos (
    video_id INT PRIMARY KEY AUTO_INCREMENT,
    youtube_video_id VARCHAR(255) UNIQUE NOT NULL,
    title VARCHAR(255),
    description TEXT,
    channel_title VARCHAR(255),
    published_at DATETIME,
    thumbnail_url VARCHAR(255),
    video_url VARCHAR(255)
);

CREATE TABLE WatchHistory (
    watch_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    video_id INT,
    watch_date DATETIME,
    FOREIGN KEY (user_id) REFERENCES Users(user_id),
    FOREIGN KEY (video_id) REFERENCES Videos(video_id)
);

CREATE TABLE LikedVideos (
    liked_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    video_id INT,
    like_date DATETIME,
    FOREIGN KEY (user_id) REFERENCES Users(user_id),
    FOREIGN KEY (video_id) REFERENCES Videos(video_id)
);

CREATE TABLE Subscriptions (
    subscription_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    channel_title VARCHAR(255),
    channel_url VARCHAR(255),
    subscribe_date DATETIME,
    FOREIGN KEY (user_id) REFERENCES Users(user_id)
);

CREATE TABLE Comments (
    comment_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    video_id INT,
    comment_text TEXT,
    comment_date DATETIME,
    FOREIGN KEY (user_id) REFERENCES Users(user_id),
    FOREIGN KEY (video_id) REFERENCES Videos(video_id)
);

CREATE TABLE Playlists (
    playlist_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    playlist_title VARCHAR(255),
    playlist_description TEXT,
    playlist_url VARCHAR(255),
    created_date DATETIME,
    FOREIGN KEY (user_id) REFERENCES Users(user_id)
);

CREATE TABLE PlaylistVideos (
    playlist_video_id INT PRIMARY KEY AUTO_INCREMENT,
    playlist_id INT,
    video_id INT,
    added_date DATETIME,
    FOREIGN KEY (playlist_id) REFERENCES Playlists(playlist_id),
    FOREIGN KEY (video_id) REFERENCES Videos(video_id)
);
