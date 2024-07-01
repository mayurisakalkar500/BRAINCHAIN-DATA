CREATE TABLE Users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    linkedin_id VARCHAR(255) UNIQUE NOT NULL,
    first_name VARCHAR(255),
    last_name VARCHAR(255),
    headline VARCHAR(255),
    summary TEXT,
    profile_url VARCHAR(255),
    location VARCHAR(255),
    industry VARCHAR(255),
    email VARCHAR(255)
);

CREATE TABLE JobHistory (
    job_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    title VARCHAR(255),
    company_name VARCHAR(255),
    location VARCHAR(255),
    start_date DATE,
    end_date DATE,
    description TEXT,
    FOREIGN KEY (user_id) REFERENCES Users(user_id)
);

CREATE TABLE Education (
    education_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    school_name VARCHAR(255),
    degree VARCHAR(255),
    field_of_study VARCHAR(255),
    start_date DATE,
    end_date DATE,
    description TEXT,
    FOREIGN KEY (user_id) REFERENCES Users(user_id)
);

CREATE TABLE Skills (
    skill_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    skill_name VARCHAR(255),
    endorsements_count INT,
    FOREIGN KEY (user_id) REFERENCES Users(user_id)
);

CREATE TABLE Recommendations (
    recommendation_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    recommender_name VARCHAR(255),
    recommender_position VARCHAR(255),
    recommendation_text TEXT,
    date DATE,
    FOREIGN KEY (user_id) REFERENCES Users(user_id)
);

CREATE TABLE Connections (
    connection_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    connection_linkedin_id VARCHAR(255),
    connection_name VARCHAR(255),
    connection_profile_url VARCHAR(255),
    connection_headline VARCHAR(255),
    FOREIGN KEY (user_id) REFERENCES Users(user_id)
);
