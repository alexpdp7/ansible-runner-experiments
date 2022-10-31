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

```
>>> ansible_runner.run(module="ansible.builtin.debug", module_args="msg=baz", host_pattern="localhost", private_data_dir=".", process_isolation=True, container_image="localhost/ansible-execution-env:latest")
```

Copy a valid kubeconfig file to the project directory and:

```
>>> ansible_runner.run(module="kubernetes.core.k8s_info", module_args="kind=pod", host_pattern="localhost", private_data_dir=".", process_isolation=True, container_image="localhost/ansible-execution-env:latest", envvars={"K8S_AUTH_KUBECONFIG": "kubeconfig"})
```
