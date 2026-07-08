# v2dat.exe
**v2dat.exe**（用于解包 V2Ray 的 `geoip.dat` / `geosite.dat` 数据包），它的 `unpack` 命令格式如下：

```
v2dat.exe unpack <类型> [参数] <dat文件>
```

其中 `<类型>` 有两个：

*   `geoip`：解包 IP 数据（geoip.dat）
*   `geosite`：解包域名规则（geosite.dat）

---

### 1\. 解包 geoip.dat

例如：

```
v2dat.exe unpack geoip geoip.dat
```

执行后会在当前目录生成类似：

```
geoip_xxx.txt
```

的文本文件。

指定输出目录：

```
v2dat.exe unpack geoip -o output geoip.dat
```

结果会放到：

```
output\
```

目录。

---

### 2\. 解包 geosite.dat

例如：

```
v2dat.exe unpack geosite geosite.dat
```

会把域名规则拆成文本文件。

---

### 3\. 只解包指定标签（filter）

比如只导出 `cn`：

```
v2dat.exe unpack geosite -f cn geosite.dat
```

多个标签：

```
v2dat.exe unpack geosite -f cn -f google geosite.dat
```

如果标签带属性：

```
v2dat.exe unpack geosite -f cn@ads geosite.dat
```

`-f` 不指定时，会导出全部标签。

---

### 4\. Windows 示例

假设：

```
D:\v2dat\v2dat.exe
D:\v2dat\geosite.dat
```

打开 CMD：

```
cd /d D:\v2dat

v2dat.exe unpack geosite -o out geosite.dat
```

生成：

```
D:\v2dat\out\
    geosite_cn.txt
    geosite_google.txt
    ...
```

---

如果你运行的是某个 **特定版本的 v2dat.exe**（例如 sing-box/v2rayN 附带的那个），参数可能略有不同，可以在目录执行：

```
v2dat.exe -h
```

或：

```
v2dat.exe unpack -h
```
