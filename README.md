# Spinner

Package spinner is a simple package to add a spinner to an application.

[![GoDoc](https://godoc.org/github.com/briandowns/spinner?status.svg)](https://godoc.org/github.com/briandowns/spinner)

For more detail about the library and its features, reference your local godoc once installed.

Contributions welcome!

## Installation

```bash
go get github.com/briandowns/spinner
```

## Available Character Sets
(Numbered by their index in the slice)

0. ←↖↑↗→↘↓↙
1. ▁▃▄▅▆▇█▇▆▅▄▃
2. ▖▘▝▗
3. ┤┘┴└├┌┬┐
4. ◢◣◤◥
5. ◰◳◲◱
6. ◴◷◶◵
7. ◐◓◑◒
8. .oO@*
9. |/-\
10. ◡◡⊙⊙◠◠
11. ⣾⣽⣻⢿⡿⣟⣯⣷
12. >))'> >))'>  >))'>   >))'>    >))'>   <'((<  <'((< <'((<
13. ⠁⠂⠄⡀⢀⠠⠐⠈
14. ⠋⠙⠹⠸⠼⠴⠦⠧⠇⠏
15. abcdefghijklmnopqrstuvwxyz
16. ▉▊▋▌▍▎▏▎▍▌▋▊▉
17. ■□▪▫
18. ←↑→↓
19. ╫╪
20. ⠋⠙⠹⠸⠼⠴⠦⠧⠇⠏
21. ⇐⇖⇑⇗⇒⇘⇓⇙
22. ⠁⠁⠉⠙⠚⠒⠂⠂⠒⠲⠴⠤⠄⠄⠤⠠⠠⠤⠦⠖⠒⠐⠐⠒⠓⠋⠉⠈⠈
23. ⠈⠉⠋⠓⠒⠐⠐⠒⠖⠦⠤⠠⠠⠤⠦⠖⠒⠐⠐⠒⠓⠋⠉⠈
24. ⠁⠉⠙⠚⠒⠂⠂⠒⠲⠴⠤⠄⠄⠤⠴⠲⠒⠂⠂⠒⠚⠙⠉⠁
25. ⠋⠙⠚⠒⠂⠂⠒⠲⠴⠦⠖⠒⠐⠐⠒⠓⠋
26. ｦｧｨｩｪｫｬｭｮｯｱｲｳｴｵｶｷｸｹｺｻｼｽｾｿﾀﾁﾂﾃﾄﾅﾆﾇﾈﾉﾊﾋﾌﾍﾎﾏﾐﾑﾒﾓﾔﾕﾖﾗﾘﾙﾚﾛﾜﾝ

## Features

Start
Stop
Restart
Reverse direction
Update the spinner character set
Update the spinner speed
Prefix or append text

## Examples

```Go
package main

import (
	"github.com/briandowns/spinner"
	"time"
)

func main() {
	s := spinner.New(spinner.CharSets[9], 100*time.Millisecond) // Build our new spinner
	s.Start()                                                    // Start the spinner
	time.Sleep(4 * time.Second)                                  // Run for some time to simulate work
	s.Stop()
}
```

## Update the spinner and restart the spinner

```Go
s.UpdateCharSet(spinner.CharSets[1])  // Update spinner to use a different character set
s.Restart()                           // Restart the spinner
time.Sleep(4 * time.Second)
s.Stop()
```

## Update spin speed and restart the spinner

```Go
s.UpdateSpeed(200 * time.Millisecond) // Update the speed the spinner spins at
s.Restart()
time.Sleep(4 * time.Second)
s.Stop()
```

## Reverse the direction of the spinner

```Go
s.Reverse() // Reverse the direction the spinner is spinning
s.Restart()
time.Sleep(4 * time.Second)
s.Stop()
```

## Provide your own spinner

(or send me an issue or pull request to add to the project)

```Go
someSet := []string{"+", "-"}
s := spinner.New(someSet, 100*time.Millisecond)
```

## Prefix or append text to the spinner

```Go
s.Prefix = "prefixed text: " // Prefix text before the spinner
s.Suffix = "  :appended text" // Append text after the spinner
```

## Generate a sequence of numbers

```Go
setOfDigits := spinner.GenerateNumberSequence(25)    // Generate a 25 digit string of numbers
s := spinner.New(setOfDigits, 100*time.Millisecond)
```
