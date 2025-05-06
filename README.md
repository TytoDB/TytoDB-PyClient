# TytoDB PyClient
This package is a connection handler client to abstract TytoDB connection process, it has support to all the
features available with the database.

## Installation
To install the package, run:
```bash
pip install tytodb-pyclient
```

## Usage
The connection handler just send a command to the database execute and return a result, for more information about the commands, seek the TytoDB documentation
```python
# Import the necessary module from your package
from tytodb_client import TytoDBClient

# Create a connection to the TytoDB instance
client = TytoDBClient(host="your-tytodb-host", port=12345, username="your-username", password="your-password")

# Example of how to get a list of available rows from a table
result = client.query("SEARCH * FROM your_container")

# Process the result
for row in result:
    print(row)

# Example of using the client to insert a new row
client.query("CREATE ROW ['row_name'][0] ON 'your_container'")

# Close the connection when done
client.close()
```
## Requirements
- Python 3.6+

## Dependencies:
- blake3
- cffi
- cryptography

