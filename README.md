# User Data Package

The **User Data Package** is a Python module that provides an interface for managing user information and settings on a Windows system. It allows you to retrieve the current user's name, manage user permissions, and handle user preferences effectively.

## Features

- Retrieve the current user's name.
- Access user permissions (e.g., check if the user is an admin).
- Manage user settings stored in a configuration file (INI format).
- Easily extendable to add more user-related functionalities.

## Installation

1. Clone the repository or download from PyPi:
   ```bash
   git clone https://github.com/aidmet/user_data.git
   cd users
   ```

2. No additional dependencies are required for this package as it uses built-in libraries.

## Usage

Here's how to use the `users` package:

```python
from users import get_current_user_name, User
from users.permissions import UserPermissions
from users.settings import UserSettings

# Create a User instance
username = get_current_user_name()
user = User(username)

# Check user permissions
permissions = UserPermissions(user)
print(f"Is {user.get_username()} an admin? {permissions.is_admin()}")
print(f"Privileges: {permissions.get_user_privileges()}")

# Manage user settings
user_settings = UserSettings(user)

# Set a new setting
user_settings.set_setting('theme', 'dark')

# Retrieve the setting
theme = user_settings.get_setting('theme', 'light')
print(f"User theme setting: {theme}")
```

## Testing

The package includes a set of unit tests to ensure functionality. To run the tests:

1. Navigate to the project directory.
2. Run the following command:
   ```bash
   python -m unittest discover -s tests
   ```

## Contributing

Contributions are welcome! If you have suggestions or improvements, please create an issue or submit a pull request.

1. Fork the repository.
2. Create your feature branch:
   ```bash
   git checkout -b feature/YourFeature
   ```
3. Commit your changes:
   ```bash
   git commit -m 'Add some feature'
   ```
4. Push to the branch:
   ```bash
   git push origin feature/YourFeature
   ```
5. Open a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Python](https://www.python.org/) - The programming language used.
- [unittest](https://docs.python.org/3/library/unittest.html) - The built-in library for testing.