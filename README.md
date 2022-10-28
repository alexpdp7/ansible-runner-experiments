```
$ ./build-venv
```

```
$ ./.venv/bin/ipython
>>> import ansible_runner
>>> ansible_runner.run(playbook="dummy-playbook.yml", private_data_dir=".")
```
