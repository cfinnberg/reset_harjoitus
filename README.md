# Harjoittele `git reset`

### Valmistele kansio

Luo kansio ja siirry siihen.
Windowsissa (PowerShell ja cmd), voit tehdä:
```
md gittest
cd gittest
```
Linuxissa ja Macissa, voit tehdä:
```
mkdir gittest
cd gittest
```

### Luo repo

Kopio ja suorittaa seuraava pätkä:
```
git init
echo "v1" > version
git add .
git commit -m "v1"

echo "v2" > version
git add .
git commit -m "v2"

echo "v3" > version
git add .
git commit -m "v3"

echo "v4" > version
git add .
git commit -m "v4"

echo "v5" > version
git add .
git commit -m "v5"

echo "v6" > version
git add .

echo "v7" > version
```

### Tarkista tilane

Tarkista `version` -tiedoston sisältö:
```
cat version
```
Jos käytät CMD, voit tehdä sitä tällä tavalla:
```
type version
```

Tarkista `git`in tilanne:
```
git status
```

Tarkista eroa staging -alueen tiedostosta työtilan tiedostoon:
```
git diff
```
(Jos staging -alueen on tyjä, se käyttää sen sijaan viimeisen committin tiedostoa)

Tarkista eroa viimeisen committin tiedostosta staging -alueen tiedostoon:
```
git diff --staged
```

Tarkista loki:
```
git log --oneline
```

### Palauta vanha versio `--soft` parametrilla

Palauta edellisen versio:
```
git reset --soft HEAD^
```

Ja tarkista tilanne niillä komennoilla, mitä nähtiin aikaisemmin:
- Työtilan tiedoston sisältö on "v7"
- Staging -alueen tiedoston sisältö on "v6"
- HEAD viittaa "v4" -committiin

### Palauta vanha versio `--mixed` parametrilla

Palauta edellisen versio:
```
git reset --mixed HEAD^
```

Ja tarkista tilanne niillä komennoilla, mitä nähtiin aikaisemmin:
- Työtilan tiedoston sisältö on "v7"
- Staging -alueen on tyhjä
- HEAD viittaa "v3" -committiin

### Palauta vanha versio `--hard` parametrilla

Palauta edellisen versio:
```
git reset --hard HEAD^
```

Ja tarkista tilanne niillä komennoilla, mitä nähtiin aikaisemmin:
- Työtilan tiedoston sisältö on "v2"
- Staging -alueen on tyhjä
- HEAD viittaa "v2" -committiin
