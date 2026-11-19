
## 一、使用scp
### 1. 复制单个文件到本地

```bash
scp username@remote_host:/path/to/remote/file.txt /path/to/local/dir/
```

### 2. 复制整个文件夹到本地

```bash
scp -r username@remote_host:/path/to/remote/folder /path/to/local/dir/
```
### 3. 上传单个文件

上传制定文件

```bash
scp /path/to/local/file.txt username@remote_host:/path/to/remote/dir/
```

**上传当前目录下的文件**：

```bash
scp file.txt username@remote_host:/home/username/
```
### 4. 上传整个文件夹（使用 `-r` 递归）

```bash
scp -r /path/to/local/folder username@remote_host:/path/to/remote/dir/
```

## 二、使用 `rsync`

对于大文件、大量文件或不稳定的网络连接，`rsync` 远优于 `scp`。

### 1. 复制单个文件到本地

```bash
rsync -avzP username@remote_host:/path/to/remote/file.txt /path/to/local/dir/
```

### 2. 复制文件夹到本地

```bash
rsync -avzP username@remote_host:/path/to/remote/folder /path/to/local/dir/

rsync -avzP orangepi@192.168.5.109:/home/orangepi/bags/ /home/yummy/UAV_NAV/data/bags/test-bags/raw_data/
```

### 3. 上传单个文件

```bash
rsync -avzP /path/to/local/file.txt username@remote_host:/path/to/remote/dir/
```

### 4. 上传文件夹

```bash
rsync -avzP /path/to/local/folder username@remote_host:/path/to/remote/dir/
```

 **注意末尾斜杠 `/` 的区别**：
 - `folder`（不带斜杠）：会在本地目标路径下创建名为 `folder` 的文件夹。
- `folder/`（带斜杠）：只会把该目录下的**所有内容**复制过去，不会在本地多套一层 `folder` 目录名。     

常用选项说明
- `-a`：归档模式，保留文件权限、属主、修改时间、软链接等属性。
- `-v`：输出详细传输日志（verbose）。  
- `-z`：传输时启用压缩，加速网络传输。
- `-P`：包含 `--progress`（显示进度条）和 `--partial`（保留断点文件，支持**断点续传**
