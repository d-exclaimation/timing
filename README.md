# Timing

Wrapping Library to perform common timing callbacks

## Usage

Haven't made this to work with mix at all

### Manual
1. Clone / Copy all the files in a directory in your project
2. Add to supervision tree
```elixir
def start(_type, _args) do
  children = [
    # Timing function seperate thread task capabilities
    {Timing.Supervisor, name: Timing.Supervisor},
  ]
  # ... your stuff here
end
```
```
3. Use the Timing to perform setTimeout and setInterval etc
```elixir
ref = Timing.timeout(2000, fn ->
  # ... Some stuff here
end)

# ...

Timing.clear(ref) # Cancel callback
```

