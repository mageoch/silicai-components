# SilicAI Components

Copyright 2026 mageo services Ltd — Licensed under the [PolyForm Noncommercial License 1.0.0](LICENSE). Commercial use requires a [separate license](https://github.com/mageoch/silicai/blob/main/COMMERCIAL_LICENSE.md).

Community component library for [SilicAI](https://github.com/mageoch/silicai).

## Structure

```
components/
├── mcu/            Microcontrollers
├── mpu/            Application processors
├── analog/         Op-amps, comparators, ADCs, DACs
├── power/          Power management ICs and discretes
├── logic/          Logic ICs
├── sensor/         Sensors
├── passive/        Resistors, capacitors, inductors
├── connector/      Connectors
└── discrete/       Transistors, diodes, MOSFETs
```

Each component is a single YAML file named after its MPN (lowercase), organized by `category/manufacturer/`.

## Validation

All component files must validate against the [SilicAI schema](https://mageoch.github.io/silicai/).

```bash
# Install silicai (e.g. cloned as a sibling directory)
uv pip install -e ../silicai

# Validate a single component
silicai-validate components/mcu/nordic/nrf52840-qdaa-r.yaml

# Validate all components
silicai-validate components/**/*.yaml
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines. Key rules:
- Files go under `components/<category>/<manufacturer>/`, named after the MPN (lowercase)
- All fields must match the datasheet exactly
- Every file must pass `silicai-validate` before submission
