# DRM Blockchain README

## Overview

This project is an implementation of a Digital Rights Management (DRM) system using blockchain technology. The code in `main.py` defines a simple blockchain-based DRM system where users can buy and sell digital images while ensuring the security and authenticity of the images using steganography and cryptographic techniques. This README provides an overview of the project, its components, and how to use the code.

## Contents

1. **Project Structure**
2. **Blockchain Implementation**
3. **Steganography with LSB**
4. **User Management**
5. **How to Use**
6. **API for Blockchain Access**

## 1. Project Structure

The project is organized into several components:

- **LSB**: This class handles the Least Significant Bit (LSB) steganography technique for embedding text data within images.
- **User**: Represents a user in the system and manages their information, including their name and fingerprint.
- **Block**: Represents a block in the blockchain. Each block contains image data, a timestamp, and a reference to the previous block.
- **Blockchain**: Manages the blockchain, including block creation, mining, and validation.
- **Flask API**: Provides a simple web API to access the blockchain data.

## 2. Blockchain Implementation

The project includes a basic blockchain implementation with the following features:

- **Proof of Work (PoW)**: Mining new blocks requires solving a PoW puzzle by finding a hash that meets a certain difficulty level.
- **Block Validation**: Each block's integrity is verified by checking its hash and the previous block's reference.
- **Transaction Handling**: Users can add a new transaction (image) to the blockchain by specifying the seller, buyer, and the image itself.

## 3. Steganography with LSB

Steganography is used to hide information within images without significantly altering their appearance. The `LSB` class is responsible for encoding and decoding information within images using the least significant bit of pixel color values. In this project, it's used to embed the buyer's fingerprint within the purchased image.

## 4. User Management

Each user is represented by the `User` class, which includes their name and a fingerprint generated from a provided fingerprint string. The fingerprint is hashed using SHA-256 to ensure user identity.

## 5. How to Use

To use the DRM system, follow these steps:

1. Import the necessary modules from `main.py`.
2. Create user objects for sellers and buyers.
3. Encode a fingerprint within an image using steganography.
4. Add a new transaction (image) to the blockchain, specifying the seller, buyer, and the image.
5. Mine a new block to confirm the transaction.
6. Access the blockchain data through the Flask API.

## 6. API for Blockchain Access

The provided Flask API allows you to access blockchain data. After running the Flask application, you can access the following endpoints:

- `/chain`: Get information about the entire blockchain, including the blocks and their details.

### Example API Usage:

- To view the blockchain, access `http://localhost:3000/chain` in your web browser.

## Conclusion

This DRM system uses blockchain technology and steganography to create a secure and traceable environment for buying and selling digital images. Users can create transactions and mine blocks to confirm them. The included Flask API makes it easy to interact with the blockchain data. Feel free to further customize and extend this code to meet your specific requirements.