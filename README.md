# Alembic Cheat Sheet

Alembic is a database migration tool for SQLAlchemy, which simplifies managing changes to database schemas over time. This cheat sheet provides a quick reference for common commands and usage patterns in Alembic.

## Installation

To install Alembic, you can use pip:

```bash
pip install alembic
```

## Getting Started

1. **Initialize Alembic:** To start using Alembic in your project, you need to initialize it. Run the following command in your project directory:

    ```bash
    alembic init alembic
    ```

2. **Configuration:** Alembic will generate a directory named `alembic` with configuration files. Modify the `alembic.ini` file to configure your database connection.

3. **Generate a Migration Script:** Use the following command to generate a new migration script after making changes to your SQLAlchemy models:

    ```bash
    alembic revision --autogenerate -m "Description of changes"
    ```

4. **Apply Migrations:** Once you've generated a migration script, you can apply it to your database:

    ```bash
    alembic upgrade head
    ```

## Common Commands

- **Creating a Revision:** Generate a new migration script:

    ```bash
    alembic revision --autogenerate -m "Description"
    ```

- **Applying Migrations:** Apply all available migrations:

    ```bash
    alembic upgrade head
    ```

- **Rolling Back Migrations:** Roll back the last migration:

    ```bash
    alembic downgrade -1
    ```

- **Viewing Migration History:** List all available migrations and their status:

    ```bash
    alembic history
    ```

- **Viewing the Current Revision:** Check the current revision of the database:

    ```bash
    alembic current
    ```

## Configuration Options

- **alembic.ini:** The main configuration file for Alembic. You can specify the database connection string and other settings here.

- **env.py:** Configuration for the Alembic environment. You can customize Alembic behavior by modifying this file.

## Advanced Usage

- **Customize Migration Templates:** You can customize the templates used to generate migration scripts by modifying the `env.py` file and specifying custom templates.

- **Multiple Database Support:** Alembic supports managing migrations for multiple databases. You can specify different database connections for different environments in the `alembic.ini` file.

- **Versioning and Tagging:** You can tag specific revisions to mark important milestones in your database schema evolution. Use the `alembic tag` command to tag revisions.

## Resources

- [Alembic Documentation](https://alembic.sqlalchemy.org/en/latest/)
- [SQLAlchemy Documentation](https://docs.sqlalchemy.org/en/20/)

## License

This cheat sheet is provided under the MIT License. See the LICENSE file for details.
