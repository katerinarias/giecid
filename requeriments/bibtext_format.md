# Tipos de entradas BibTeX

## Revista (`@article`)
```bibtex
@article{identificador,
  author = {Apellido, Nombre},
  title = {Título del artículo},
  journal = {Nombre de la revista},
  year = {año},
  volume = {volumen},
  number = {número},
  pages = {rango de páginas},
  doi = {DOI}
}
```

## Libro (`@book`)
```bibtex
@book{identificador,
  author = {Apellido, Nombre} o editor = {Apellido, Nombre},
  title = {Título del libro},
  publisher = {Editorial},
  year = {año},
  address = {Ciudad o país},
  edition = {edición},
  isbn = {ISBN}
}
```

## Capítulo de Libro (`@incollection` o `@inbook`)
```bibtex
@incollection{identificador,
  author = {Apellido, Nombre del autor del capítulo},
  title = {Título del capítulo},
  booktitle = {Título del libro},
  editor = {Apellido, Nombre del editor del libro},
  publisher = {Editorial},
  year = {año},
  chapter = {número de capítulo (opcional)},
  pages = {rango de páginas},
  address = {Ciudad o país}
}
```