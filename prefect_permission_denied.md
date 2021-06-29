# Prefect permission denied

Documenting a solution to an error durring the installation Prefect: 
https://docs.prefect.io/core/getting_started/installation.html

At step:

```shell
sudo prefect server start
```
```shell
Traceback (most recent call last):
  File "/home/nico/code/prefect-test/venv/bin/prefect", line 8, in <module>
    sys.exit(cli())
  File "/home/nico/code/prefect-test/venv/lib/python3.8/site-packages/click/core.py", line 829, in __call__
    return self.main(*args, **kwargs)
  File "/home/nico/code/prefect-test/venv/lib/python3.8/site-packages/click/core.py", line 782, in main
    rv = self.invoke(ctx)
  File "/home/nico/code/prefect-test/venv/lib/python3.8/site-packages/click/core.py", line 1259, in invoke
    return _process_result(sub_ctx.command.invoke(sub_ctx))
  File "/home/nico/code/prefect-test/venv/lib/python3.8/site-packages/click/core.py", line 1259, in invoke
    return _process_result(sub_ctx.command.invoke(sub_ctx))
  File "/home/nico/code/prefect-test/venv/lib/python3.8/site-packages/click/core.py", line 1066, in invoke
    return ctx.invoke(self.callback, **ctx.params)
  File "/home/nico/code/prefect-test/venv/lib/python3.8/site-packages/click/core.py", line 610, in invoke
    return callback(*args, **kwargs)
  File "/home/nico/code/prefect-test/venv/lib/python3.8/site-packages/prefect/cli/server.py", line 578, in start
    compose_path = setup_compose_file(
  File "/home/nico/code/prefect-test/venv/lib/python3.8/site-packages/prefect/cli/server.py", line 188, in setup_compose_file
    shutil.copy2(base_compose_path, temp_path)
  File "/usr/lib/python3.8/shutil.py", line 435, in copy2
    copyfile(src, dst, follow_symlinks=follow_symlinks)
  File "/usr/lib/python3.8/shutil.py", line 264, in copyfile
    with open(src, 'rb') as fsrc, open(dst, 'wb') as fdst:
PermissionError: [Errno 13] Permission denied: '/tmp/docker-compose.yml'
```

I'm On Arch Linux using community package Docker 1:20.10.7-1.  
Running a docker requires `sudo`, for example `sudo docker run hello-world` works fine.

So my intuition was that this file `/tmp/docker-compose.yml` would need to be readable by `root`.

So I changed its permissions:
```shell
sudo chown -R root:root /tmp/docker-compose.yml
```

And now the server start works without error and I can load the web interface.
