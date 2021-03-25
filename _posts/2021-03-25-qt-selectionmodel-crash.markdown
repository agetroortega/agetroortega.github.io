---
layout: post
title: "Qt selection model crashing"
date: 2021-03-25
description: Testing description
image: /assets/images/plane_crash.jpg
author: Fernando Ortega
tags:
  - Qt
  - pyqt
  - coding 
---

I spent the past 15 minutes debugging the following snippet of code, it was crashing my application
with no traceback!

All I wanted to do was connect a signal when the selection on my tree view changes.

```python
self.view = QTreeView()
self.view.selectionModel().currentChanged.connect(self.some_slot)
```

The **solution** was to simply keep track of the selection model
```python
# test comment
self.view - QTreeView()
self.selectionModel = selectionModel()
self.selectionModel.currentChanged.connect(self.some_slot)
```

Hope this saved you some time!

This will work with any subclass of QAbstractItemView (QTableView, QTreeView, etc.)


> [Photo by Matheus Bertelli from Pexels]