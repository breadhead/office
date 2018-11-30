# Установка peer-dependencies

Чтобы устанавливать peer-dependencies без боли, мы используем библиотеку [install-self-peers](https://github.com/team-griffin/install-self-peers)

## Install

```
npm i --save-dev @team-griffin/install-self-peers

yarn add --dev @team-griffin/install-self-peers
```

## Usage

### Manual

```
./node_modules/.bin/install-self-peers
```

### Package.json lifecycle

```
{
  "scripts": {
    "prepare": "install-self-peers -- --ignore-scripts"
  }
}
```