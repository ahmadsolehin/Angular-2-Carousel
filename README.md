# Ng2Carouselamos

Ng2-carouselamos is a simple carousel/slider which just use css transitions to do the work

### Demo
![Demo](2017-06-29_18-02-13.gif)

### Getting started
- Install node package:
```
npm i ng2-carouselamos --save
```

And then, in your app.module.ts :
```
import { Ng2CarouselamosModule } from 'ng2-carouselamos';
...
@NgModule({
  ...
  imports: [
    ...
    Ng2CarouselamosModule
  ],
  ...
})
```

### Documentation
  ```ng2-carouselamos``` - attribute to apply carousel

  ```width``` - size of window to show

  ```items``` - objects array that belong to the carousel

  ```$item``` - template for each item

  ```$prev``` - template for previous button

  ```$next``` - template for next button

  ```onSelectedItem($event)``` - event triggered when snap element. $event is an object containing the current item and the current index - { item: ..., index: ... }


  Inside ```$item``` template we have access to the follow:

  * ```let-item``` - the current element of the objects array

  * ```let-i="index"``` - current index  


### Implementing
```html
<div
  ng2-carouselamos
  [width]="500"
  [items]="listOfItems"
  [$item]="itemTemplate"
  [$prev]="prevTemplate"
  [$next]="nextTemplate"
  (onSelectedItem)="selectedItem = $event.item; selectedIndex = $event.index"
></div>

<div>
  Current item selected
</div>

<ng-template #prevTemplate>
  <img src="prev.png" />
</ng-template>

<ng-template #nextTemplate>
  <img src="next.png" />
</ng-template>

<ng-template let-item let-i="index" #itemTemplate>
  <div style="min-width: 200px">
    <b *ngIf="i === selectedIndex">{{i}}. {{item.name}}</b>
    <span *ngIf="i !== selectedIndex">{{i}}. {{item.name}}</span>
  </div>
</ng-template>
```

## screenshot

![nn](https://user-images.githubusercontent.com/12325386/28809358-914b365a-76b5-11e7-9491-5856e7d781f7.JPG)
