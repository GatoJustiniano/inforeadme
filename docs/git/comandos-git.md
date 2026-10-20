# Comandos frecuentes de Git

## Crear y subir un repositorio

```
git init
git add -A
git commit -m "comentario"
git push origin main        # antes la rama principal se llamaba master
```

## Actualizar

```
git pull                    # actualiza el repositorio local
git pull upstream main      # actualiza un fork desde el repositorio original
```

## Deshacer

```
git reset --hard HEAD^      # vuelve al commit anterior (¡descarta los cambios!)
```

## Ver también

* [Comandos frecuentes de Laravel](docs/laravel/comandos-laravel.md)
