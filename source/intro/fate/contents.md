# [fate项目](https://github.com/kaoputou/fate)


### 技术栈
- Programming Langugge
    - Python3.7

- Web Framework
    - Flask

- Package Management
    - pip

- Database + ORM + Migration
    - Postgresql
    - SQLAlchemy
    - Alembic

- Cache
    - Redis + Flask-Cache

- Offline Job
    - Celery + Redis(broker)

- Web Server
    - Gunicorn + werkzeug

- Testing
    - Unit / Integration Test: pytest

- CI/CD
    - GitHub Actions (in the future)


### 项目风格
fate 项目使用 pre-commit 来统一项目的代码风格。相关配置文件写在 `.pre-commit-config.yaml` 中。

pre-commit 的安装:
```bash
pip install pre-commit
```

pre-commit 初始化
```
git rev-parse --quiet --verify HEAD && pre-commit install -t commit-msg
```

pre-commit 会在当前路径 .git/hooks 下生成配置文件，并且在 git commit 的时候，对提交的内容做检查。
如果想要跳过检查，可以执行如下命令
```bash
git commit -m 'commit message' -n
or
git comit -m 'commit message' --no-verify
or
PRE_COMMIT_ALLOW_NO_CONFIG=1  git commit -m 'commit message'
```

如果想要在项目中删除 pre-commit，需要删除对应的配置文件
```bash
rm -rf .git/hooks
```


### 包管理
fate 项目使用 pip 来管理第三方包的安装，安装包放置在 `requirement.txt` 文件中。
```bash
pip install -r requirement.txt
```

### 测试
fate 项目使用 pytest 来做测试(单元测试 + 集成测试), 测试相关代码位于 `tests/` 路径。项目使用 make 来执行测试

运行所有的测试用例:
```bash
make test
```

CICD 测试并输出代码覆盖率:
```bash
make ci-test
```

另外，pytest 也支持运行单个测试文件或者单个测试用例，例如，

运行单个测试文件
```bash
pytest -s 'test_file_path'
```

运行单个测试用例
```bash
pytest -k 'testcase_name'
```

具体请参考 [pytest](https://docs.pytest.org/) 官网。


### 参考
- [pre-commit](https://pre-commit.com/)
- [pytest](https://docs.pytest.org/)
