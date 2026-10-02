# Kancelaria notarialne X&Y — strona z panelem administracyjnym

Projekt demonstracyjny (firma i dane są fikcyjne). Realizacja: Strony AI Wrocław — Grzegorz, stronywroclawai@gmail.com

Strona to jeden plik `index.html` (HTML, CSS i JS w środku). Nie wymaga budowania ani serwera.

## Pliki

| Plik | Do czego służy |
|---|---|
| `index.html` | cała strona wraz z panelem administracyjnym |
| `_headers` | nagłówki bezpieczeństwa dla Cloudflare Pages |
| `robots.txt` | blokuje indeksowanie wersji demonstracyjnej |
| `.gitignore` | pliki pomijane przez Git |
| `README.md` | ta instrukcja |

## 1. GitHub

Przez przeglądarkę:

1. Na github.com wybierz **New repository**, nazwa np. `kancelaria-notarialne-x-y`, potem **Create repository**.
2. Kliknij **uploading an existing file**, przeciągnij wszystkie pliki z tego folderu (także `_headers` i `.gitignore`) i wybierz **Commit changes**.

Albo z terminala, w tym folderze:

```
git init
git add .
git commit -m "Strona kancelarii"
git branch -M main
git remote add origin https://github.com/TWOJ-LOGIN/kancelaria-notarialne-x-y.git
git push -u origin main
```

## 2. Cloudflare Pages

1. W panelu Cloudflare otwórz **Workers & Pages → Create → Pages → Connect to Git**.
2. Wybierz repozytorium z GitHuba.
3. Ustawienia budowania: **Framework preset: None**, **Build command: puste**, **Build output directory: /**.
4. Kliknij **Save and Deploy**. Strona pojawi się pod adresem `nazwa-projektu.pages.dev`.

Każda zmiana wysłana na gałąź `main` wdraża się automatycznie.

Bez GitHuba: **Workers & Pages → Create → Pages → Upload assets** i przeciągnij ten folder.

## 3. Własna domena

W projekcie Pages otwórz **Custom domains → Set up a custom domain** i podaj domenę.

## Ważne przed publikacją dla prawdziwego klienta

- Panel jest w wersji demonstracyjnej: login `admin`, hasło `notariusz` są zapisane w kodzie, a zmiany z panelu zapisują się tylko w przeglądarce osoby edytującej. Inni odwiedzający ich nie zobaczą.
- Żeby zmiana z panelu trafiła na opublikowaną stronę, trzeba ją wpisać do danych początkowych w `index.html` (sekcja „1. DANE POCZĄTKOWE”) i wysłać plik ponownie.
- Podmień dane przykładowe: adres, zespół, godziny otwarcia, telefon i e-mail.
- W `robots.txt` zamień `Disallow: /` na `Allow: /`.
- Usuń dopisek o projekcie demonstracyjnym ze stopki (tekst `demo` w `index.html`).
- Statystyki odwiedzin: kod narzędzia wklej przed `</body>`.
