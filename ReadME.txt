安装方式：
1) cd到当前目录
2) python setup.py install

将中文时间描述转换为三种标准的时间格式的时间字符串：
1) 时间点（timestamp，表示某一具体时间时间描述）; 
2) 时间量（timedelta，表示时间的增量的时间描述）; 
3) 时间区间（timespan，有具体起始和结束时间点的时间区间）。
调用示例见Test.py

若出现字符编码问题，请检查当前编码环境是否为utf-8，或使用如下代码：
import sys
reload(sys)
sys.setdefaultencoding('utf8')

关于节假日的增加方法：
1) 在resource目录下的holi_lunar(阴历)或holi_solar(阳历)文件内按照格式加入新增的节日名称和日期
2) 在resource目录下的regex.txt文件内加入相应节日的正则匹配，并删除regex.pkl缓存文件
3) 在TimeUnit类中的norm_setHoliday方法同样加入节日的正则匹配