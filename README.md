# AndroidMountNas
由于本人特别希望能有种方法使得NAS能挂载到手机上，由于Ehviewer中的下载选项中，是直接打开安卓原生的文件系统，因此是没有Nas的这种选项的。再加上如果要实现手机直接挂载cifs的功能，一种是直接刷第三方涵盖cifs的rom，或者在手机上通过挂载linux系统再在linux系统上挂载smb。由于操作不当，第二种方法未能成功。

在  https://github.com/xiaojieonly/Ehviewer_CN_SXJ/issues/378 中我曾经使用google store上的cifs文件管理系统成功挂载，但是也正如所说的，只能访问浏览，不能直接下载到nas上

在此提出一种新的方法，本方法应该无需越狱适合所有安卓手机，也给后来者提供启发

google曾经推出过一款应用叫Android Samba Client,但目前在play store上已下架，但仍可在互联网中找到，输入smb的链接smb:\\ip\目录，在此说明，只能是一层目录，否则会报错

成功挂载后，通过ehviewer是可以下载的，但是进度条不会变，通过打开路径可知，下载的文件是没有后缀的，但如果我们将其加上.jpg即可浏览，猜测可能是ehviewer的下载方式问题

因此如果能够实现边下载完成后立马将文件改为.jpg文件应该是可以和下载到手机路径是一样的

有一款应用叫inotify，可以实现实时监测文件的变化，通过检测eh文件夹的变化来实现修改

通过bash脚本即可实现将下载的文件转成jpg文件,配合着ehviewer使用应该是没有问题的，bash脚本内容如下：

![contents](https://github.com/BaG-Ray/AndroidMountNas/raw/master/1.png)

