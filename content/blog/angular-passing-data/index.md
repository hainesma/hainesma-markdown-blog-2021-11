---
title: Passing Data Between Components in Angular
tags: Angular
author: Mark Haines
date: 10/17/2021
---

There are two situations I want to cover:
- Passing data from parent to child components, where the child component is rendered within the parent component, and;
- Passing data between sibling components, where we navigate away from the first component and to the second.


## Passing data to a sibling component

Suppose we have a list of items. In the list, a ```preview-card``` component is rendered for each item. We want users to be able to click on an item's card and go to a ```details-page```. We need to find a way to tell that details page component which item to put into its template. 

I like to do this by creating a *service*, which will store the object while we switch components.

Steps:
1. Create the service using the Angular CLI.
```
ng generate service data
```

*data.service.ts*:

```
import { Injectable } from '@angular/core';
import { Item } from './item';

@Injectable({
  providedIn: 'root'
})

export class DataService {
  public item: Item;
}
```

2. Inject the service into the constructor of both sibling components.

*preview-card.component.ts* and *details-page.component.ts*:

```
import { DataService } from '../data.service';
.
.
.
constructor(public dataService: DataService) { }
```

3. Use the component life cycle to store and retrieve the object.

*preview-card.component.ts*:

```
ngOnDestroy() {
    this.dataService.item = this.cardItem;
}
```


*details-page.component.ts*:

```
ngOnInit() {
    this.pageItem = this.dataService.item;
}
```

4. Add the link to the template of the first sibling component.


*preview-card.component.ts*:

```
<a [routerLink]="['/details-page']"></a>
```