```
$ ./build-venv
```

This will only work if `ansible-playbook` is somewhere in your path.

```
$ ./.venv/bin/ipython
>>> import ansible_runner
>>> ansible_runner.run(playbook="dummy-playbook.yml", private_data_dir=".")
```

But this will use podman and the `quay.io/ansible/ansible-runner:devel` image automatically.
It will work even if you do not have the `ansible-playbook` installed.

```
>>> ansible_runner.run(playbook="dummy-playbook.yml", private_data_dir=".", process_isolation=True)
```

```
$ ./create-ee
```
