
# Basic Blockchain

A simple blockchain implementation with basic proof of work and peer-to-peer communication using Python and Flask. This project demonstrates the fundamental concepts of a blockchain, including mining blocks, validating the chain, and adding transactions.

## Features

- **Proof of Work**: Simple proof of work algorithm to simulate mining.
- **Blockchain Validation**: Ensures the integrity and validity of the blockchain.
- **Transactions**: Allows the addition of transactions to the blockchain.
- **Peer-to-Peer Communication**: Nodes can connect and synchronize with each other.

## Installation

1. **Clone the repository**:
   ```sh
   git clone https://github.com/yourusername/basic-blockchain.git
   cd basic-blockchain
   ```

2. **Create a virtual environment** (optional but recommended):
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install the required packages**:
   ```sh
   pip install Flask requests
   ```

## Usage

1. **Run the Flask application**:
   ```sh
   python blockchain.py
   ```

2. **Interact with the blockchain**:
   - **Mine a new block**:
     ```sh
     curl -X GET http://127.0.0.1:5000/mine_block
     ```
   - **Get the full blockchain**:
     ```sh
     curl -X GET http://127.0.0.1:5000/get_chain
     ```
   - **Check if the blockchain is valid**:
     ```sh
     curl -X GET http://127.0.0.1:5000/is_valid
     ```
   - **Add a new transaction**:
     ```sh
     curl -X POST http://127.0.0.1:5000/add_transaction -H "Content-Type: application/json" -d '{"sender": "address1", "receiver": "address2", "amount": 10}'
     ```
   - **Connect new nodes**:
     ```sh
     curl -X POST http://127.0.0.1:5000/connect_node -H "Content-Type: application/json" -d '{"nodes": ["http://127.0.0.1:5001"]}'
     ```
   - **Replace the chain with the longest chain**:
     ```sh
     curl -X GET http://127.0.0.1:5000/replace_chain
     ```

## Endpoints

- **`GET /mine_block`**: Mines a new block and adds it to the blockchain.
- **`GET /get_chain`**: Returns the entire blockchain.
- **`GET /is_valid`**: Checks if the blockchain is valid.
- **`POST /add_transaction`**: Adds a new transaction to the blockchain.
- **`POST /connect_node`**: Connects new nodes to the network.
- **`GET /replace_chain`**: Replaces the chain with the longest chain in the network.

## Examples

### Mine a New Block

```sh
curl -X GET http://127.0.0.1:5000/mine_block
```

**Response**:
```json
{
    "message": "Congratulations, you just mined a block!",
    "index": 2,
    "timestamp": 1638253993.757,
    "proof": 35293,
    "previous_hash": "6a7d5f3b3f6b8a9d6a6c5b7a5c7d6a5b7a5c7d6a5b7c5a6d5a7b6c5d6a5c7d6a",
    "transactions": []
}
```

### Get the Full Blockchain

```sh
curl -X GET http://127.0.0.1:5000/get_chain
```

**Response**:
```json
{
    "chain": [
        {
            "index": 1,
            "timestamp": 1638253993.757,
            "proof": 100,
            "previous_hash": "1",
            "transactions": []
        },
        {
            "index": 2,
            "timestamp": 1638253993.757,
            "proof": 35293,
            "previous_hash": "6a7d5f3b3f6b8a9d6a6c5b7a5c7d6a5b7a5c7d6a5b7c5a6d5a7b6c5d6a5c7d6a",
            "transactions": []
        }
    ],
    "length": 2
}
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- Inspired by various blockchain tutorials and implementations.
- Thanks to the open-source community for their contributions.

---

Developed with 💻 by [Abdul Sahil](https://github.com/abdulsaheel)

