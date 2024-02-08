  <h1>Personal Data Handling Module</h1>
    <p>This Python module is designed to handle personal data securely by providing functionalities for logging and database operations while ensuring sensitive information is redacted appropriately. It includes features for filtering and obfuscating personally identifiable information (PII) from log messages and interacts with a MySQL database to retrieve and log user data.</p>
    <h2>Usage</h2>
    <p>The module includes the following functionalities:</p>
    <ul>
        <li><strong>Filtering Personal Data:</strong> The <code>filter_datum()</code> function is used to obfuscate sensitive data within log messages. It takes a list of fields to redact, a redaction string, the original message, and a separator as input, and returns the message with sensitive information obfuscated.</li>
        <li><strong>Logging Personal Data:</strong> The <code>get_logger()</code> function initializes a logging instance configured to redact specified PII fields using the <code>RedactingFormatter</code> class.</li>
        <li><strong>Database Connection:</strong> The <code>get_db()</code> function establishes a connection to a MySQL database, retrieving database credentials from environment variables or using default values.</li>
        <li><strong>Main Functionality:</strong> The <code>main()</code> function connects to the configured database, retrieves all rows from the users table, and logs each row's data with sensitive information redacted.</li>
    </ul>
    <h2>Environment Variables</h2>
    <p><strong>PERSONAL_DATA_DB_USERNAME:</strong> Username for accessing the MySQL database. Defaults to "root" if not provided.</p>
    <p><strong>PERSONAL_DATA_DB_PASSWORD:</strong> Password for accessing the MySQL database. No default value; must be provided.</p>
    <p><strong>PERSONAL_DATA_DB_HOST:</strong> Host address of the MySQL database. Defaults to "localhost" if not provided.</p>
    <p><strong>PERSONAL_DATA_DB_NAME:</strong> Name of the MySQL database. No default value; must be provided.</p>
      <h1>Password Hashing Functions</h1>
    <h2>hash_password(password: str) -&gt; bytes:</h2>
    <p>Hashes the provided plaintext password using bcrypt with a randomly generated salt.</p>
    <p>Returns the hashed password as a byte string.</p>
    <h2>is_valid(hashed_password: bytes, password: str) -&gt; bool:</h2>
    <p>Validates whether the provided plaintext password matches the hashed password.</p>
    <p>Returns a boolean indicating the validity of the password.</p>