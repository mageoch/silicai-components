# SilicAI Components

Community component library for [SilicAI](https://github.com/mageoch/silicai).

## Structure

```
components/
├── mcu/            Microcontrollers
├── power/          Power management ICs and discretes
├── analog/         Op-amps, comparators, ADCs, DACs
├── wireless/       RF and wireless modules
├── passive/        Resistors, capacitors, inductors
├── connector/      Connectors
└── discrete/       Transistors, diodes, MOSFETs
```

Each component is a single YAML file named after its MPN (lowercase), organized by `category/manufacturer/`.

## Validation

```bash
pip install -e ../silicai
silicai-validate components/mcu/st/stm32f405rgt6.yaml
```

## Contributing

All component files must validate against the schema in [mageoch/silicai](https://github.com/mageoch/silicai).
