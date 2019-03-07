CSS 방법론 - BEM(Block Element Modifier)
=======================================

# 정의
* BEM은 Block Element Modifier의 약자이다.
* 태그, ID는 사용할 수 없고, class명만 사용할 수 있다.
* .header__navigation‐‐secondary과 같은 class를 사용한다.

# 작명규칙(Naming Convention)
* 개발, 디버깅, 유지보수를 위해 css선택자의 이름을 가능한 한 명확하게 만드는 것이 목표이다.
* 소문자와 숫자 만을 이용해서 작명한다.
* 여러단어의 조합은 하이픈(-)으로 연결하여 작명한다.

# 블록(Block)
* block은 문단 전체에 적용된 element 또는 element를 담고 있는 컨테이너를 말한다.
* 형태(red, big)가 아닌 목적(menu, button)에 맞게 결정한다.
* 블록은 환경에 영향을 받지 않아야 한다. 즉, 여백이나 위치를 설정하면 안된다.
* 블록은 서로 중첩해서 작성할 수 있다.
* 예) header, menu, search-form..

```
<div class="header">
    <div class="menu">....</div>
    <div class="search">....</div>
</div>
```

# 요소(Element)
* 블록안에서 특정 기능을 담당하는 부분.
* block__element 형태로 사용(더블 언더바)
* 형태(red, big)가 아닌 목적(item, text, title)에 맞게 결정해야 한다.
* 요소는 중첩해서 작성할 수 있다.
* 요소는 블록의 부분으로만 사용 할 수 있고 다른 요소의 부분으로 사용할 수 없다.
* 모든 블록에서 요소는 필수가 아닌 선택적으로 사용한다. 즉 블록안에 요소가 없을 수도 있다.
* 예) header__logo, header__menu, block-name__element-name...

# 수식어(Modifier)
* 외관이나 상태의 변화 : 블록이나 요소의 모양(color, size..), 상태(disabled, checked..)를 정의한다.
* block__element--modifier, block--modifier 형태로 사용(더블 하이픈)
* 수식어의 __블리언 타입__과 __키-벨류__ 타입이 있다.
    - 블리언 타입: 수식어가 있으면 값이 true라고 가정한다. (form__button--disabled)
    - 키-벨류 타입: 키, 벨류를 하이픈으로 연결하여 표시한다.(color-red, theme-ocean)
* 수식어는 단독으로 사용할 수 없다. 즉 기본 블록과 요소에 추가하여 사용해야 한다.(class="block__element block__element--modifire")

# 혼합사용(Mix)
* block, block2__element 형태로 사용할 수 있다.
* block2__element에 여백이나 위치를 지정하고 block1은 독립적으로 유지할
수 있다.

```
<div class="header">
    <div class="search-form header__search-form"></div>
</div>
```

* BEM의 class명은 구체적이고 명료하여 HTML안에서도 읽기 쉬워야 한다.
* BEM은 클래스 명이 길게 이어지므로 css 작성보다 sass나 less를 이용하는 것이 효율적이다.
* class명이 무엇을 나타내는지 분명하게 전달돼야 한다.


[BEM](https://en.bem.info/)

[BEM File Structure](https://en.bem.info/methodology/filestructure/)

[BEM을 깨우치다](https://www.slideshare.net/UyeongJu/bem-52783817)
