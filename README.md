# AutoCheckTool

这个项目主要是为了解决收作业时繁杂的检查步骤。我经常遇到以下情况：

1. 对着班级名单（Excel）挨个检查每位同学是否提交了文件。
2. 每次收作业都要反复进行（1），十分浪费时间。

于是，就有了这个项目。

## Description

已经实现的功能有：

- [x] 根据`名单.xlsx`来确定某同学是否交作业了。
- [x] 根据`pyproject.toml`中的`path`来扫描需要检查的文件夹
- [x] 基础的shell交互
- [x] 手动输入path来扫描文件夹
- [x] 打包成可执行文件并加入环境变量

未来可能会实现的功能有：

- [ ] 更友好的shell交互
- [ ] GUI界面
- [ ] 指定根目录扫描所有子目录
- [ ] 用NLP对学号姓名匹配进行校验




## 开始

### 依赖

* Package: `toml`，`tomlkit`，`openpyxl`
* Environment: Windows 10+，Python3.9

### 可执行文件
[下载地址](https://github.com/Alkaidcc/AutocheckTool/releases/tag/v0.0.1)

下载`ack.exe`和pyproject.toml后，只需修改配置文件即可运行


### 自己构建

```shell
git clone https://github.com/Alkaidcc/AutocheckTool.git
```

```python
pip install -r requirements.txt
```

### 修改配置文件

- 填写`pyproject.toml`中的`ScanPath`和`XlsxPath`
- 例子
  - XlsxPath = 'D:\Develop\Py\test.xlsx'
  - ScanPath = ['path1','path2']

#### pyproject.toml

```toml
[tool.config]
XlsxPath = 'D:\Develop\Py\test.xlsx'
ScanPath = ['path1','path2']
```
修改path1,path2……为你需要扫描的路径


#### test.xlsx格式

| ID    | NAME  |
| ----- | ----- |
| 学号1 | 姓名1 |
| 学号2 | 姓名2 |
| ...   | ...   |

### 启动

```shell
python ack.py
```

## Tips
该项目检查时根据.xlsx文件中的学号匹配检查目录下的文件，请务必确保文件夹中的文件名包含学生学号。
## Help

欢迎提出pr和issues。

## Authors

[@Alkaidcc](https://github.com/Alkaidcc)

## License

This project is licensed under the [MIT] License - see the `LICENSE` file for details
