def check_access(user, resource):
    # Define a list of tuples representing the permissions matrix
    permissions = [
        ("admin", "all", True),
        ("user", "read", True),
        ("user", "write", False),
    ]
    for permission in permissions:
        if user == permission[0] and resource == permission[1]:
            return permission[2]
    return False

def main():
    # Example usage
    user = "user"
    resource = "read"
    if check_access(user, resource):
        print(f"Access granted for user {user} to resource {resource}")
    else:
        print(f"Access denied for user {user} to resource {resource}")
