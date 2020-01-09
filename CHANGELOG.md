# Changelog

## 2.0.0

Changed persist and attach of workspace to use the root of the `working_directory`.

You will have to change your persist to:
```yaml
- persist_to_workspace:
    root: ~/workdir
    paths:
    - '*'
```

and your attach to:
```yaml
- attach_workspace:
    at: ~/workdir
```

when `~/workdir` is your `working_directory`.
