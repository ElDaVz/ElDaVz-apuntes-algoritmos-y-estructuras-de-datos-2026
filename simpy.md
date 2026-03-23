# Simpy (Python)

## Ejemplo 3

```python
import simpy
import random

RANDOM_SEED = 42
NEW_CUSTOMERS = 10 # Total number of customers
INTERVAL_CUSTOMERS = 10.0 # Generate new customers roughle every x seconds
MIN_PATIENCE = 1 # Min. customer patience
MAX_PATIENCE = 3 # Max. customer patience

def source(env, number, interval, counter):
    """Source generates customers randomly"""
    for i in range(number):
        c = customer(env, 'Customer%02d' % i, counter, time_in_bank=12.0)
        env.process(c)
        t = random.expovariate(1.0 / interval) # tiempo en ser atendido
        yield env.timeout(t)
```

```python
def customer(env, name, counter, time_in_bank):
    """Customer arrives, is served and leaves.""
```

## Ejemplo 1

```python
def car(nombre, env):

```

| t   | a   | b   |
| --- | --- | --- |
| 0s  | P4  | P1  |
| 1s  | P2  | D2  |
| 2s  | P4  | P1  |
| 3s  | P3  | D4  |
