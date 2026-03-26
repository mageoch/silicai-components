# Contributing to SilicAI Components

Thank you for contributing a component definition. This library grows through
community submissions — every validated component file is useful to someone.

## Licensing

By submitting a contribution you agree that your work will be licensed under
the same terms as this repository (PolyForm Noncommercial License 1.0.0) and
that mageo services Ltd may offer it under commercial licenses as described
in the [SilicAI commercial license](https://github.com/mageoch/silicai/blob/main/COMMERCIAL_LICENSE.md).

## Adding a component

1. **Find the right location** — files go under `components/<category>/<manufacturer>/`
   using lowercase MPN as the filename (e.g. `components/sensor/ti/tmp117aidrvr.yaml`)

2. **Write the component file** — follow the schema at
   [mageoch/silicai](https://github.com/mageoch/silicai). At minimum include:
   - `mpn`, `manufacturer`, `category`, `package`
   - All pins with `number`, `name`, and `direction`
   - Power rails with decoupling requirements
   - Communication interfaces if applicable

3. **Validate** — the file must pass validation before submission:
   ```bash
   pip install silicai
   silicai-validate components/<category>/<manufacturer>/<mpn>.yaml
   ```

4. **Source your data** — all values must come from the official datasheet.
   Add the `datasheet` URL field so reviewers can verify.

5. **Open a pull request** — one component per PR is preferred. Include the
   datasheet link in the PR description if not already in the file.

## Data quality

- Values must match the datasheet exactly — do not guess or interpolate
- Use the correct units (`V`, `mA`, `nF`, `kHz`, `Ω`, `°C`, etc.)
- Include `absolute_maximum_ratings` and `recommended_operating_conditions`
  when they are clearly stated in the datasheet
- Mark pins `must_connect: true` if the datasheet explicitly states the pin
  must not be left floating

## Questions

Open an issue or reach out at [info@mageo.ch](mailto:info@mageo.ch).
