PAWN-Scanner
============

A code scanner for PAWN. Finds function declarations, enumerations, constants, and more.

# Demo usage

```PHP
include 'PAWNScanner.php';

$scanner = new PAWNScanner\Scanner();

$scanner->scan_dir('include', 'a_npc.inc');

// Most things can be casted to strings
echo $scanner->functions['SetPlayerPos'] . "\n";

// They're split into pieces, however.
echo $scanner->functions['SetPlayerPos']->name . "\n";
echo $scanner->functions['SetPlayerPos']->arguments . "\n";

// Argument lists are subclasses of VariableList.
echo $scanner->functions['SetPlayerPos']->arguments->variables[1] . "\n";
echo $scanner->functions['SetPlayerPos']->arguments->variables[1]->tags . "\n";
```

**Output**:

```
native SetPlayerPos(playerid, Float:x, Float:y, Float:z)
SetPlayerPos
playerid, Float:x, Float:y, Float:z
Float:x
Float
```