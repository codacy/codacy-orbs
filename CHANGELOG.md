# Changelog

## 2.0.0

Changed persist and attach of workspace to use the root of the `working_directory`.

Currently when you `attach_workspace` you will always have a directory called `workdir`,
which does not allow you to `attach_workspace` in a directory that does not have forcefully `workdir` inside.

This change allows for `attach_workspace` to not depend on the `working_directory` name.

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

when `~/workdir` is your `working_directory`, after this change your attach could be anything you wanted,
since it does not depend on `working_directory` name.
