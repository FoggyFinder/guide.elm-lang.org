# Вступ до Elm

**Elm - це функціональна мова, яка компілюється в JavaScript.** Вона конкурує з такими проектами як React, виконуючи роль інструменту для створення веб-сайтів та веб-додатків. Elm робить дуже сильний акцент на простоту, зручність у використанні та якість інструментів.

Це керівництво:
  - Навчить вас основам програмування в Elm.
  - Продемонструє, як робити інтерактивні додатки з використанням *Elm архітектури*.
  - Підкреслить загальні принципи і закономірності, які характерні для програмування на будь-якій мові.

Зрештою, я сподіваюся, що ви будете не тільки мати можливість створювати великі веб-додатки в Elm, але і розуміти основні ідеї та шаблони проектування, які роблять Elm чудовим у використанні.

Якщо ви вже на борту, я можу легко вам гарантувати, що якщо ви надасте Elm шанс та насправді зробите проект на ньому, у кінці кінців ви зможете писати набагато кращий код на JavaScript та React.

## Швидкий Приклад

Звичайно *я* вважаю Elm добрим, тож подивіться самі.

Ось [простий лічильник](http://elm-lang.org/examples/buttons). Якщо ви зазирнете у код, то побачите, що він дозволяє просто збільшувати та зменшувати значення лічильника:

```elm
import Html exposing (Html, button, div, text)
import Html.Events exposing (onClick)

main =
  Html.beginnerProgram { model = 0, view = view, update = update }

type Msg = Increment | Decrement

update msg model =
  case msg of
    Increment ->
      model + 1

    Decrement ->
      model - 1

view model =
  div []
    [ button [ onClick Decrement ] [ text "-" ]
    , div [] [ text (toString model) ]
    , button [ onClick Increment ] [ text "+" ]
    ]
```

Зверніть увагу на те, що `update` та `view` цілком відокремлені. Ви описуєте ваш HTML декларативно і Elm піклується про наведення порядку з DOM.

## Чому *функціональна* мова?

Забудьте, що ви коли-небудь чули про функціональне програмування. Незвичні слова, дивні ідеї, погані інструменти. Ні. Elm це:

  - Жодних помилок при виконанні на практиці. Ніяких `null`. Ніяких `undefined` is not a function.
  - Привітні та дружелюбні повідомлення про помилку допоможуть вам додавати функціонал швидше.
  - Добре спроектований код, що *залишається* добре спроектованим у той самий час, як ваш додаток росте.
  - Автоматичне примусове сематичне версіонування для всіх пакетів Elm.

Жодна комбінація бібліотек JavaScript не дасть вам цього, але все це ви безкоштовно та просто отримуєте з Elm. Ці чудові речі є можливими *тільки* через те, що Elm базується на 40+ роках праці в області функціональних мов. Таким чином, Elm це функціональна мова, тому що практичні переваги варті кілька годин, які ви витратите на це керівництво.

Я зробив величезний акцент на тому, щоб зробити Elm легким для вивчання та користування, тому все, що я питаю від вас, це дати Elm шанс та подивитись, що ви про нього думаєте. Я сподіваюсь, що ви будете приємно здивовані!
