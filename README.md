# bubbletea
This shows a bug affecting bubbletea TUI where nested sequence commands are not sequential

### Description
The **expected** result should look like:
```


    Searching for something...
  ──────────────────────────────




  Something is not loaded!
  Something is loaded!
```

Change line 58 in `main.go` to:
```go
return m, tea.Sequence(tea.Batch(func() tea.Msg {
```

... to see the correct result
