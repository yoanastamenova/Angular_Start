# AngularStart

STEPS TO FOLLOW TO CREATE ANGULAR PROJECT

https://github.com/yoanastamenova/Angular_Start.git

# STEPS TO FOLLOW WHEN WORKING WITH REACT 

<div align="center">
<img src="https://img.shields.io/badge/angular-%23DD0031.svg?style=for-the-badge&logo=angular&logoColor=white">
</div>

## START REPOSITORY

1. ` ng new my-app `

2. Choose options such as:
    - styles format, 
    - share info, 
    - SS Rendering  
    ` cd my-app `
    ` npm start `

3. We can now open the provided port as in our browser 
` localhost:4200 `

## START AMENDING FILES

4. By default, the main files you'll be working on are:

- src/app/app.component.html (for the template)
- src/app/app.component.ts (for the logic)
- src/app/app.component.css (for styling)

5. In app.component.ts, modify the selector, templateUrl, or styleUrls as needed.

6. To declare variables (called properties in Angular), add them inside the AppComponent class in app.component.ts:
``` export class AppComponent { name: string = 'Your name here'; } } ```

7. In app.component.html, you can bind this variable to the template using Angular interpolation:
``` <h1>{{ name }}</h1> ```

## CREATE NEW COMPONENT

We can either use the CLI or creating files ourselfs

With the CLI:

8. Write in the terminal
``` ng generate component component-name ```

This will generate the following structure inside the src/app folder:

- component-name/ folder
- component-name.component.ts
- component-name.component.html
- component-name.component.css
- component-name.component.spec.ts

9. Using the new component:
- To use the component inside app.component.html, you need to include the selector:
``` <app-component-name></app-component-name> ```

- The selector is defined in component-name.component.ts:
``` 
@Component({
  selector: 'app-component-name',
  templateUrl: './component-name.component.html',
  styleUrls: ['./component-name.component.css']
})
```
10. Passing data to the component (similar to React props):
- In component-name.component.ts, use the @Input() decorator to accept data from the parent component:
```
import { Component, Input } from '@angular/core';

@Component({
  selector: 'app-title',
  templateUrl: './title.component.html',
  styleUrls: ['./title.component.css']
})
export class TitleComponent {
  @Input() name: string;
}

```

- In title.component.html, display the passed value:

```
<h1>{{ name }}</h1>
```

- In app.component.html, pass the name value to the child component:

```
<app-title [name]="name"></app-title>
```

--------

Via creating files

11. In src create a new folder with the name of the component

12. Create one file for the component logic
```
name.component.ts
```

13. Inside use the following info:
```
import { Component } from '@angular/core';

@Component({
  selector: 'app-header',
  standalone: true,
  templateUrl: './name.component.html'
})
```

14. After that add it to the core component which is - app.component.html file
```
<app-name></app-name>
```

15. Next add it to the app.component.ts file
```
import {NameComponent} from './name.component';
...
imports:[NameComponent]
```

16. To link styles for our component we create name.component.css and link it inside name.component.ts
```
styleUrl: './name.component.css'
```
