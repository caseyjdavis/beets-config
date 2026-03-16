## Set up a Python virtual environment

```bash
python3 -m venv ~/.venv/beets
source ~/.venv/beets/bin/activate
```

## Install beets

```bash
pip install beets
```

## Install the plugins too

```bash
pip install python3-discogs-client pylast
```

## Copy the config.yaml file to your home dir

```bash
cp config.yaml ~/.config/beets/
```

## Import your music folder into beets

```bash
beet import /Music
```

## Dismount the virtual environment

```bash
deactivate
```

## Remount the virtual environment later

```bash
source ~/.venv/beets/bin/activate
```
