import hashlib

def generate_md5(message):
    """
    Generates the MD5 hash of a given message (string).

    Args:
        message (str): The input text to be hashed.

    Returns:
        str: The 32-character hexadecimal MD5 hash digest.
    """
    # 1. Initialize the MD5 hash object
    md5_hash = hashlib.md5()
    
    # 2. Update the hash object with the encoded message
    # Hashing algorithms work on bytes, so the string must be encoded.
    md5_hash.update(message.encode('utf-8'))
    
    # 3. Return the hash digest as a hexadecimal string
    return md5_hash.hexdigest()

if __name__ == "__main__":
    # Get user input
    text = input("Enter text to hash using MD5: ")
    
    # Generate the MD5 hash
    md5_result = generate_md5(text)
    
    # Print the results
    print(f"\nOriginal Text: \"{text}\"")
    print(f"MD5 Hash: {md5_result}")