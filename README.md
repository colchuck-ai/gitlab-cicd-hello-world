# gitlab-cicd-hello-world

The purpose of this [gitlab cicd component](https://docs.gitlab.com/ee/ci/components/) project is to publish a component that prints "hello world", and introduces itself using a name defined by and input.

## Contents

- [gitlab-cicd-hello-world](#gitlab-cicd-hello-world)
  - [Contents](#contents)
  - [Components](#components)
    - [`hello-world` Component](#hello-world-component)
    - [`hello-world` Component Inputs](#hello-world-component-inputs)
    - [`hello-world` Component Usage](#hello-world-component-usage)

## Components

### `hello-world` Component

The `hello-world` component creates a single hidden job `.hello-world`, that prints "hello world", and introduces itself using a name defined by and input.

### `hello-world` Component Inputs

| Name   | Type     | Description                                | Required | Default |
| ------ | -------- | ------------------------------------------ | -------- | ------- |
| `name` | `string` | The name of the robot that will greet you. | no       | `Hal`   |

### `hello-world` Component Usage

```yml
include:
  - component: gitlab.example.com/engineering/dev-tools/gitlab-cicd-components/gitlab-cicd-hello-world/hello-world@1.0.0

stages:
  - greeting

greeting:
  stage: greeting
  extends:
    - .hello-world
```

## Disclaimer

We built this because we needed it. We welcome contributions. If you want to consume the artifacts released by this project, do so with the same consideration you would take when consuming an open source component.
