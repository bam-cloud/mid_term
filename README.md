# mid_term

Use of Design Patterns
* Consistent Structure: Each plugin is organized within its own directory, ensuring a uniform structure. This consistency enhances maintainability and improves the overall understanding of the project's layout.
* DRY Principle (Don't Repeat Yourself): The code eliminates redundant logic and unnecessary repetition. For instance, in the CalcCommand and HistoryCommand classes, functionalities are encapsulated within dedicated methods, preventing duplication across different sections of the code.
* Single Responsibility Principle (SRP): Each class is designed to fulfill a distinct responsibility. For example, CalcCommand handles calculations, HistoryCommand manages the history of calculations, and HistoryReplCommand facilitates an interactive REPL for history management.
* Open/Closed Principle (OCP): The design allows for extensibility without modifying existing code. New commands or operations can be introduced by extending existing classes or adding new dictionary entries, preserving the integrity of the current implementation.
* Liskov Substitution Principle (LSP): Command classes such as CalcCommand, HistoryCommand, and HistoryReplCommand conform to the Command interface by implementing the execute method. This ensures they can be substituted interchangeably wherever a Command is required.
* Dependency Inversion Principle (DIP): The implementation relies on abstractions instead of concrete dependencies. For instance, command classes depend on the abstract Command class, while the App class interacts with the abstract CommandHandler for registering and executing commands.
* Separation of Concerns: The responsibilities are well-defined and separated. The App class manages the overall application setup and plugin loading, command classes handle user-specific commands, and the Calculator class is dedicated to arithmetic operations.
* Facade Pattern and Command Pattern: The code provides a simplified interface through the REPL, enabling efficient calculation and history management using structured commands. This approach streamlines complex Pandas data manipulations.
Overall, the adherence to these design principles results in a well-structured, maintainable, and scalable codebase.


Use of Environment Variables
* Loading Environment Variables: At the start of main.py, the load_dotenv() function from the dotenv package is utilized to load environment variables from a .env file into the application's environment.
* Accessing Environment Variables: These variables are accessed using os.getenv(). For instance, the application retrieves the environment mode and logging level from the APP_ENV and LOG_LEVEL environment variables, respectively.
* Flexibility and Configuration: By leveraging environment variables, the application becomes more adaptable and easily configurable across different environments (e.g., development, testing, production) without requiring modifications to the code.
Link:   

Use of Logging
1. Importing the Logging Module: At the beginning of the main.py file, the logging module, along with other necessary modules, is imported for logging configuration.
2. Loading the Logging Configuration: The fileConfig function from the logging.config module is used to load the logging settings from the logging.conf file.
3. Creating a Logger: A logger instance is initialized using the getLogger function to manage log messages throughout the application.
4. Using the Logger: The logger is utilized across the main.py file to record messages at different severity levels. For example, logger.debug logs debugging details, logger.info captures general information, and logger.error records error messages.
5. Logging Configuration File (logging.conf): This configuration file defines the setup for loggers, handlers, and formatters. It specifies that log messages should be stored in a file (logs/app.log) and formatted with a timestamp, log level, and message.
6. Dynamic Logging: The logging level can be dynamically adjusted through environment variables and the logging.conf file to control the verbosity of log output.
By implementing logging in this manner, the application records detailed runtime information, which is crucial for debugging and monitoring. The log messages are stored in a file, making them easily accessible for later review.
