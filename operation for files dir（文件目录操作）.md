# Python-Note

Python basic knowledge notes.

具体代码如下：

import os

# 该函数会获得路径下的文件列表；
def getListFiles(path):

    ret = []  #先初始化一个空的列表；
    
    for root, dirs, files in os.walk(path):# 将os.walk在元素中提取的值，分别放到root（根目录），
    # dirs（目录名），files（文件名）中，注意：这里将入口参数path作为了root。
    
        for filespath in files:
        
            ret.append(os.path.join(root,filespath))
            
    return ret
    
if __name__ == '__main__':

    ret = getListFiles("./") # 注意"./"代表当前目录；"/"代表根目录，直接找到文件所在的根目录；"../"代表父级目录，也就是当前目录的上一层。
    
    for each in ret:
    
        print(each)
        
# 获取当前目录下所有的子目录
sub_dirs = [x[0] for x in os.walk(INPUT_DATA)]  # 注意这里的x[0]必须加上，而且不同的数字功能不同，这个可以得到
                                                #INPUT_DATA文件下的子文件夹，也就是子目录但是并不会得到子文件夹下的所有文件。
