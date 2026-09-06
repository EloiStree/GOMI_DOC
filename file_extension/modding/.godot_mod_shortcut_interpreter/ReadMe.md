Shortcut are words without any space.

The interpretors in the application claim the words they understand to execute some code.

If you dont care of other interpreter.
Use the any format: `.godot_mod_shortcut_any`



Can you handle the word ?
```
func is_able_to_interpret_given_word(word: String) -> bool:
	return false
```

Execute the given word that you said you can handle
```
func interpret_given_word(word: String) -> void:
	pass
```


```gdscript
extends Node

# Code 

func is_able_to_interpret_given_word(word: String) -> bool:
	return _dictionary_keyword_to_url.has(word)

func interpret_given_word(word: String) -> void:
	if not _dictionary_keyword_to_url.has(word):
		return
	var url = _dictionary_keyword_to_url[word]
	if url == "":
		return
	OS.shell_open(url) 

```