# Redis

## Startup

Launch an interactive elixir REPL in the repo directory.

```bash
$ iex -S mix
```

# API

```elixir
iex(1)> Cache.start_link
{:ok, #PID<0.142.0>}
iex(2)> Cache.write(:fruits, ["apples","oranges"])
:success
iex(3)> Cache.write("City of Lights", "Varanasi")
:success
iex(4)> Cache.read(:fruits)
{:success, ["apples", "oranges"]}
iex(5)> Cache.exist?("City of Lights")
true
iex(6)> Cache.exist?("Schrödinger's cat")
false
iex(7)> Cache.delete(:fruits)
:success
iex(8)> Cache.read(:fruits)
:keynotfound
iex(9)> Cache.clear
:ok
iex(10)> Cache.exist?("City of Lights")
false
iex(11)> Cache.write("FP", "❤️")
:success
iex(12)> Cache.stop
"server terminated because of :normal, cache below"
:ok
%{"FP" => "❤️"}
```
