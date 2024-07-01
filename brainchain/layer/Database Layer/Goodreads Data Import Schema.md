CREATE TABLE Users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    goodreads_id VARCHAR(255) UNIQUE NOT NULL,
    username VARCHAR(255),
    name VARCHAR(255),
    profile_url VARCHAR(255),
    location VARCHAR(255),
    joined_date DATE
);

CREATE TABLE Books (
    book_id INT PRIMARY KEY AUTO_INCREMENT,
    goodreads_book_id VARCHAR(255) UNIQUE NOT NULL,
    title VARCHAR(255),
    author VARCHAR(255),
    isbn VARCHAR(255),
    publication_date DATE,
    description TEXT,
    cover_image_url VARCHAR(255)
);

CREATE TABLE Reviews (
    review_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    book_id INT,
    rating INT,
    review_date DATE,
    review_text TEXT,
    FOREIGN KEY (user_id) REFERENCES Users(user_id),
    FOREIGN KEY (book_id) REFERENCES Books(book_id)
);

CREATE TABLE Shelves (
    shelf_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    shelf_name VARCHAR(255),
    description TEXT,
    FOREIGN KEY (user_id) REFERENCES Users(user_id)
);

CREATE TABLE ShelfBooks (
    shelf_book_id INT PRIMARY KEY AUTO_INCREMENT,
    shelf_id INT,
    book_id INT,
    FOREIGN KEY (shelf_id) REFERENCES Shelves(shelf_id),
    FOREIGN KEY (book_id) REFERENCES Books(book_id)
);

CREATE TABLE ReadingStatus (
    status_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    book_id INT,
    status VARCHAR(255),
    start_date DATE,
    end_date DATE,
    FOREIGN KEY (user_id) REFERENCES Users(user_id),
    FOREIGN KEY (book_id) REFERENCES Books(book_id)
);
//Mostly we wont take this
CREATE TABLE Friends (
    friendship_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    friend_id INT,
    friendship_date DATE,
    FOREIGN KEY (user_id) REFERENCES Users(user_id),
    FOREIGN KEY (friend_id) REFERENCES Users(user_id)
);
