1.模型初始化放在gunicorn_config中
启动时加上 --preload，启动不报错，预测报错
启动时不加 --preload 直接报错
``
RuntimeError: Cannot re-initialize CUDA in forked subprocess. To use CUDA with multiprocessing, you must use the 'spawn' start method
``
2.模型初始化放在flask app中
一切正常，除了每个worker会占用一份的显存