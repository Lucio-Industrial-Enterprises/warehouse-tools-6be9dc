# Warehouse tools

Small Python utilities for warehouse order and shipping workflows.

Run the tests with `python3 -m unittest discover -s tests -v`.

## Shipping

`shipping_quote(weight_kg, zone, service="standard")` returns a delivery quote
in US dollars.

- **zone** — `"local"` or `"regional"`.
- **service** — `"standard"` (default) or `"express"`. Express adds a flat $7
  surcharge on top of the standard rate.
- **weight_kg** — must be positive.

The command-line entry point prints a quote:

```
python -m warehouse.cli <weight_kg> <zone> [--service {standard,express}]
```

Example:

```
$ python -m warehouse.cli 2 local
$8.00
$ python -m warehouse.cli 2 local --service express
$15.00
```
