# Operativsystem - inledande datorövning

Gör följande övningar för att bli van med att använda kommandotolken och att kompilera C-kod. 

Allt kan alltså göras i Codespaces-terminalen, eller på en egen maskin.

## På egen maskin

Om du gör det på egen (virtuell) maskin, installera GCC kompilatorn med följande kommandon på Ubuntu:
1. Installera utvecklingsmiljö `sudo apt update && sudo apt install build-essentials`.
2. Installera manualen för utvecklingsmiljön `sudo apt install manpages-dev`.
3. Kontrollera om kompilatorn installerades: `gcc --version`.

## I webbläsaren med Codespaces

Då du är i repositoryn på Github, tryck den gröna knappen `Code` och `Create codespace on main`. 

Då skapas och startas en virtuell miljö (Docker container). 

En tidigare skapad Codespace-miljö kan startas från listan som vissas då man trycker på `Code`-knappen.

## Exempel på vanliga terminal-kommandon

| Kommando | Resultat |
|---|---|
| `$ pwd` | Visa sökvägen till nuvarande katalog |
| `$ ls` | Lista filer i nuvarande katalog |
| `$ ls -a` | Lista alla filer i nuvarande katalog, inklusive dolda filer |
| `$ ls -al` | Lista alla filer i nuvarande katalog med detaljer (datum, storlek, rättigheter) |
| `$ ls *.txt` | Wildcard: lista alla filer med .txt-filändelse |

| Kommando | Resultat |
|---|---|
| `$ cd ..` | Flytta upp en katalognivå |
| `$ cd ../../` | Flytta upp två katalognivåer |

| Kommando | Resultat |
|---|---|
| `$ rmdir <dir_name>` | Radera en tom katalog |
| `$ rm <file_name>` | Radera en fil |
| `$ rm -r <dir_name>` | Radera en katalog, inklusive dess innehåll; frågar efter bekräftelse, `f`-argumentet tar bort bekräftelsen |

| Kommando | Resultat |
|---|---|
| `$ mv <name1> <name2>` | Byter namn på kataloger eller filer |
| `$ mv <name> <path>` | Flyttar en fil/katalog till sökvägen som specificeras  |
| `$ rm -r <dir_name>` | Radera en katalog, inklusive dess innehåll; frågar efter bekräftelse, `f`-argumentet tar bort bekräftelsen |

| Kommando | Resultat |
|---|---|
| `$ man <kommando>` | Visar manualen för kommandot i fråga |

| Kommando | Resultat |
|---|---|
| `$ whoami` | Skriver ut namnet på nuvarande användare |

## Övningar: terminalen 

1. Skapa en katalog `lab`.
2. Läs manualen för kommandot `touch` och skapa 10 tomma filer `{car1, ..., car10}` i `lab1`-katalogen. Använd endast ett kommando.
3. Skapa en katalog `cars` i `lab1`-latalogen och skapa några underkataloger i den. 
4. Kopiera filerna `car5` och `car10` till `cars`-underkatalogen genom att använda `cp`-kommandot (använd `man` om du är osäker hur det används).
5. Kopiera katalogen `/usr/share/doc/build-essential` rekursivt till katalogen `lab` som du skapade i steg 1. 
6. Lista innehållet i `lab1`-katalogen rekursivt. Använd `less`-kommandot för att stega igenom outputen. Glöm inte `|`-tecknet!
7. Radera `car1` och `car2`.
8. Skapa en ny katalog `newcars` i `cars`-katalogen och flytta `car3` och `car4` dit.
9. Radera `newcars`-katalogen och dess innehåll.
10. Skapa en katalog `/tmp/myfinds` i `lab1`. Hitta alla filer under `/usr/share`-katalogen som är större än 5 MB och mindre än 10 MB och kopiera dem till `myfinds`.

## Övningar: C-programmering

1. Skapa en fil `hello.c` med följande innehåll (du kan t.ex. använda kommandot `code hello.c` i terminalen för att öppna ett nytt VS Code fönster).
```
#include <stdio.h>

int main() {
    printf("Hello, world!\n");
    return 0;
}
```
Kompilera koden med `gcc hello.c -o hello` och kör programmet med `./hello`.

Gör en Git-commit där du `sparar` ändringarna i filen `hello.c` till repositoryn.

2. Hur kan du modifiera koden ovan för att skriva ut "Hello World" till terminalen utan att använda någon semikolon?

3. Vad är skillnaden mellan `i++` och `++i`?

4. Vilken utskrift ger följande program
```
#include <stdio.h>

void func(int x) {
    x = 50;
}

int main() {
    int y = 40;
    func(y);
    printf("%d", y);
    return 0;
}
```

5. Vilken utskrift ger följande program?
```
#include <stdio.h>

void func(int *ptr) {
    *ptr = 50;
}

int main() {
    int y = 40;
    func(&y);
    printf("%d", y);
    return 0;
}
```

6. Vilken utskrift ger följande program?
```
#include <stdio.h>

int main()
{
    char *ptr = "Operativsystem";
    printf("%c\n", *&*&*&*ptr);
    return 0;
}
```


7. Vilken utskrift ger följande program?
```
#include <stdio.h>

int main() {
    int a[] = {1, 2, 3, 4, 5};
    int *p = a;
    ++*p;
    p += 2;
    printf("%d", *p);
    return 0;
} 
```