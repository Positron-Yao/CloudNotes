## gum

一个非常好用的tui应用制作工具，通过[gum-python](https://github.com/idobarel/gum-python.git)包接入python.

### 安装

```bash
git clone https://github.com/idobarel/gum-python
cd gum-python
sudo python3 setup.py install
```

### 函数

```python
choose(msg: str, opt: list["str"], type: object = str)
input(placeholder: str = "", is_password=True, header="", prompt="") -> str
confirm(msg: str, background_color=212, color=255) -> bool
write() -> str
search(options: list[str])
spin(title: str, time: int = 3, spinner: str = "dot")
bunner(text: str, border: str, margin: int, padding: tuple, color: int = 212)
system(command)
```

