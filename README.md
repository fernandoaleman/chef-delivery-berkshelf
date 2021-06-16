# chef-delivery-berkshelf

A Github Action to run Chef Delivery on a cookbook when using Berkshelf.

This cookbook is based on
[actionshub/chef-delivery](https://github.com/actionshub/chef-delivery) except
this one pins [chef-workstation](https://github.com/chef/chef-workstation) to
version `21.6.467`, which is the last release before Ruby 3.0. Berkshelf does
not currently support Ruby 3.0's `splat`.

This action will work with Policyfiles, but if using them, you can simply use
[actionshub/chef-delivery](https://github.com/actionshub/chef-delivery).

## Usage

```yaml
name: delivery

on: [push, pull_request]

jobs:
  delivery:

    runs-on: ubuntu-latest

    steps:
    - name: Check out code
      uses: actions/checkout@main
    - name: Run Chef Delivery
      uses: fernandoaleman/chef-delivery-berkshelf@main
```
