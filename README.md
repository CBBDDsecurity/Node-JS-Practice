# Node JS Practice 🚀

![Node.js](https://img.shields.io/badge/Node.js-8CC84B?style=flat&logo=node.js&logoColor=white) ![NPM](https://img.shields.io/badge/NPM-CB3837?style=flat&logo=npm&logoColor=white) ![GitHub Releases](https://img.shields.io/badge/Releases-v1.0.0-blue?style=flat&logo=github&logoColor=white)

Welcome to the **Node JS Practice** repository! This project serves as a practice ground for server-side programming, especially tailored for competitive programming enthusiasts. Whether you are a beginner or an experienced developer, this repository offers a variety of exercises and examples to sharpen your skills in Node.js.

## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Introduction

In today's tech landscape, mastering server-side programming is essential. This repository focuses on Node.js, a powerful JavaScript runtime that allows you to build scalable network applications. The exercises in this repository cover a wide range of topics, including file systems, HTTP requests, and more.

## Getting Started

To get started with this project, clone the repository to your local machine. You can do this using the following command:

```bash
git clone https://github.com/CBBDDsecurity/Node-JS-Practice.git
```

Next, navigate into the project directory:

```bash
cd Node-JS-Practice
```

To install the necessary dependencies, run:

```bash
npm install
```

You can find the latest releases [here](https://github.com/CBBDDsecurity/Node-JS-Practice/releases). Download the required files and execute them to explore the functionalities.

## Features

- **Crypto Module**: Learn how to use Node.js's built-in crypto module for encryption and decryption.
- **File System (fs)**: Work with files and directories, performing operations like reading, writing, and deleting.
- **HTTP Module**: Create a simple web server and handle HTTP requests and responses.
- **Postman Integration**: Test your APIs using Postman, a powerful tool for API development.
- **Query Parameters**: Understand how to handle query parameters in your applications.
- **Response Headers**: Learn how to manipulate response headers for better control over your API.
- **Streams**: Explore how to work with streams for efficient data handling.

## Technologies Used

This project utilizes a variety of technologies, including:

- **Node.js**: The core runtime for building server-side applications.
- **NPM**: The package manager for JavaScript, used to manage dependencies.
- **Lodash**: A utility library for JavaScript that simplifies common programming tasks.
- **Nodemon**: A tool that helps develop Node.js applications by automatically restarting the server when file changes are detected.

## Usage

To run the application, use the following command:

```bash
node app.js
```

Make sure to replace `app.js` with the name of the main file you wish to execute. You can also use Nodemon for automatic restarts:

```bash
nodemon app.js
```

For more detailed instructions on each module, check the corresponding files in the repository.

## Examples

### Crypto Example

```javascript
const crypto = require('crypto');

const algorithm = 'aes-256-cbc';
const key = crypto.randomBytes(32);
const iv = crypto.randomBytes(16);

const encrypt = (text) => {
    let cipher = crypto.createCipheriv(algorithm, Buffer.from(key), iv);
    let encrypted = cipher.update(text);
    encrypted = Buffer.concat([encrypted, cipher.final()]);
    return { iv: iv.toString('hex'), encryptedData: encrypted.toString('hex') };
};

const decrypted = (text) => {
    let decipher = crypto.createDecipheriv(algorithm, Buffer.from(key), Buffer.from(text.iv, 'hex'));
    let decrypted = decipher.update(Buffer.from(text.encryptedData, 'hex'));
    decrypted = Buffer.concat([decrypted, decipher.final()]);
    return decrypted.toString();
};

// Example usage
const data = encrypt("Hello, World!");
console.log(data);
console.log(decrypted(data));
```

### File System Example

```javascript
const fs = require('fs');

// Writing to a file
fs.writeFile('example.txt', 'Hello, Node.js!', (err) => {
    if (err) throw err;
    console.log('File has been saved!');
});

// Reading from a file
fs.readFile('example.txt', 'utf8', (err, data) => {
    if (err) throw err;
    console.log(data);
});
```

## Contributing

We welcome contributions to this repository! If you have suggestions or improvements, feel free to fork the repository and submit a pull request. Please ensure that your code adheres to the project's coding standards and includes appropriate tests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or feedback, please reach out via the GitHub issues page or contact the repository owner directly.

You can find the latest releases [here](https://github.com/CBBDDsecurity/Node-JS-Practice/releases). Download the required files and execute them to explore the functionalities.

---

Happy coding! 🌟