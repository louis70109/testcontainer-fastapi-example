# Example for develops FastAPI in CONTAINER with VSCode

Following are Chinese contents:
- [如何在 VSCode 中以 Container 方式開發 FastAPI + PostgreSQL](https://nijialin.com/2021/05/29/fastapi-dev-in-container-vscode/)
- [【tetcontainer】使用 Python 在 Docker 中做資料庫的測試案例 | 來賓: PostgreSQL, Docker, Python, GitHub Actions](https://nijialin.com/2021/11/25/python-testcontainer-fasstapi-database/)

## Prerequisite

- VSCode
  - Extension
    - Python
    - Remote Container
- Docker Desktop

## Development

- Open project with VSCode.
- Install `Remote - Containers` VSCode dependency.
- Press `Command` + `Shift` + `p` (Mac).
- Input `Remote Containers: Reopen in Container`.
- Left-side you will find `Run & Debug`, click it and find `►` button.
- Choose `Python: FastAPI` to run this project.
- Then bottom-side would become different color.(Mean you run success)

## License

MIT

## Backup

```
AttributeError: 'generator' object has no attribute 'query'
```

`get_db()` is not an sqlalchemy session object but rather a generator that yields a session object.

Use `next()` to wrap `get_db()`.

refs: https://stackoverflow.com/questions/65982681/how-to-access-the-database-from-unit-test-in-fast-api

### I can run Testcontainer at local, but why my LINE Bot function fail in GitHub Actions?

Because we ran LINE Bot development and testing with `.env` file for environment variable, so LINE Bot webhook could init success in testing.

Next, when your repo push to GitHub, you just set a real LINE Bot channel_access_token and channel_secret at GitHub Actions for testing, that your would success in testing.
