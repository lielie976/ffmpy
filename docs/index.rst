.. ffmpy documentation master file, created by
   sphinx-quickstart on Tue May 31 08:22:14 2016.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

ffmpy
=====
ffmpy是一个对 `FFmpeg <https://ffmpeg.org>`_ 命令的Python包装。它把提供的参数和其他选项编译成FFmpeg命令行，并用Python的 `subprocess <https://docs.python.org/3/library/subprocess.html>`_ 模块执行。

ffmpy类似于FFmpeg的命令行用法。它可以读取任意数量的输入“文件”(常规文件，管道，网络数据流，抓取设备等等)并且写入任意数量的输出“文件”。查看FFmpeg `文档 <https://ffmpeg.org/ffmpeg.html#Synopsis>`_ 获取更多关于FFmpeg命令行选项和参数的信息。

ffmpy支持FFmpeg `管道协议 <https://ffmpeg.org/ffmpeg-protocols.html#pipe>`_ 。这意味着可以传递数据到 ``标准输入`` 然后从 ``标准输出`` 得到结果数据。目前ffmpy提供了对 ``ffmpeg`` 和 ``ffmprobe`` 命令的包装，但是它应该可以运行其他的FFmpeg的工具（例如： ``ffserver``）。


安装
------------
::

  pip install ffmpy

快速示例
----------
::

  >>> import ffmpy
  >>> ff = ffmpy.FFmpeg(
  ...     inputs={'input.mp4': None},
  ...     outputs={'output.avi': None}
  ... )
  >>> ff.run()

这将会把当前路径下的 ``input.mp4`` 文件作为输入，把视频容器从 MP4 修改为 AVI 而不改变其他视频参数并在当前路径下创建一个新的输出文件``output.avi`` 。

文档说明
-------------
.. toctree::
  :maxdepth: 2

  ffmpy
  examples
