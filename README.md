# Guard Library for SCPL

Validation and guard helpers for numbers, strings, and simple value checks.

## Files

- `__init__.scpl`: exports all library functions
- `dependencies.json`: library dependencies for MLIS
- `README.md`: usage and examples

## Exported Functions

- `positive? value`
- `negative? value`
- `zero? value`
- `even? value`
- `odd? value`
- `between? value min max`
- `clamp value min max`
- `empty? value`
- `blank? value`
- `one-of? value a b c`

## Usage

```scpl
import guard
Initialize-console

Console-print: (positive? 12)       -- true
Console-print: (negative? -2)       -- true
Console-print: (zero? 0)            -- true
Console-print: (even? 8)            -- true
Console-print: (odd? 7)             -- true
Console-print: (between? 5 1 10)    -- true
Console-print: (clamp 50 0 10)      -- 10
Console-print: (empty? '')
Console-print: (blank? '')
Console-print: (one-of? 'scpl' 'js' 'py' 'scpl')

Close-console
```

## Notes

- `one-of?` currently checks up to three candidate values because SCPL does not yet support variadic user functions cleanly.
- `empty?` relies on the built-in `length`.
- Boolean-style results are returned as `true` / `false`, matching the current style used by existing SCPL libraries.
