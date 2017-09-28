# Python-Note

Python basic knowledge notes.

具体代码如下：

import os

def getListFiles(path):

    ret = []
    
    for root, dirs, files in os.walk(path):
    
        for filespath in files:
        
            ret.append(os.path.join(root,filespath))
            
    return ret
    
if __name__ == '__main__':

    ret = getListFiles("./") # 注意"./"代表当前目录；"/"代表根目录，直接找到文件所在的根目录；"../"代表父级目录，也就是当前目录的上一层。
    
    for each in ret:
    
        print(each)
