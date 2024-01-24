# Test task for "PUZZLE PRODUCTION"
developer: Артамонов Артём Александрович

## Npm scripts
Start development server
```
npm run dev
```

build project
```
npm run build
```

deploy to gh pages
```
npm run deploy
```

## Docs
#### App.vue
<ul>
   <li>компоненты ModelList и ModelForm</li>
   <li>список серверов клиентов</li>
   <li>функции выбора и замены сервера</li>
   <li>глобальные стили</li>
</ul>

#### components/ModelList.vue
<ul>
   <li>представляет из себя компонент ModelItem с заголовком</li>
   <li>цикл по серверам с ModelItem</li>
   <li>получает в props список серверов клиентов</li>
   <li>емит с выбранным сервером</li>
   <li>стили списка</li>
</ul>

#### components/ModelForm.vue
<ul>
   <li>представляет из себя заголовок и форму с компонентами FormInput и FormButton</li>
   <li>цикл по ключам выбранного сервера с FormInput</li>
   <li>получает в props выбранного сервера</li>
   <li>емит с изменением выбранного сервера</li>
   <li>стили формы</li>
</ul>

#### components/ModelItem.vue
<ul>
   <li>представляет из себя элемент списка</li>
   <li>получает в props сервер</li>
   <li>стили элемента</li>
</ul>

#### components/ModelInput.vue
<ul>
   <li>представляет из себя лейбл с полем ввода или селектом</li>
   <li>получает в props: heading (название свойства сервера), value (значение свойства сервера), disabled (булевое значение)</li>
   <li>стили элемента</li>
</ul>

#### components/ModelButton.vue
<ul>
   <li>представляет из кнопку</li>
   <li>стили элемента</li>
</ul>

#### types/types.ts
<ul>
   <li>содержит интерфейс для типизации сервера</li>
</ul>
