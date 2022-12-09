Icez
#3599

Icez — 06/10/2022 11:04
@Test     public void scoreShouldBeIncreasedByFiveWhenSnakeEatsGreenFood() throws InvocationTargetException, IllegalAccessException{         gameLoopUnderTest = new GameLoop(new Platform(), new Snake(new Point2D(0,0)), new Food(new Point2D(0,1),true));         gameLoopUnderTest.getPlatform().setKey(KeyCode.DOWN);         clockTickHelper();         clockTickHelper();         assertEquals(5,gameLoopUnderTest.getSnake().getSnakeScore());     } } เพิ่มใน Game loop test บรรทัดสุดท้าย import se233.chapter5.view.Platform; import javafx.geometry.Point2D;  import java.util.Random;  public class Food {     private Point2D position ;     private Random rn ;     private int score = 1 ;     public boolean isSpecialFood = false ;      public Food(Point2D position){         this.position = position ;         this.rn = new Random();     }     public Food(Point2D position, boolean isSpecialFood){         this.position = position ;         this.rn = new Random();         this.isSpecialFood = isSpecialF
import se233.chapter5.view.Platform;
import javafx.geometry.Point2D;

import java.util.Random;

public class Food {
    private Point2D position ;
    private Random rn ;
    private int score = 1 ;
    public boolean isSpecialFood = false ;

    public Food(Point2D position){
        this.position = position ;
        this.rn = new Random();
    }
    public Food(Point2D position, boolean isSpecialFood){
        this.position = position ;
        this.rn = new Random();
        this.isSpecialFood = isSpecialFood;
        this.score = 5 ;
    }
    public Food(){
        this.rn = new Random();
        respawn();
    }

    public void respawn() {
        Point2D prev_position = this.position;

        do{
            if(rn.nextInt(6) == 1){
                this.isSpecialFood = true ;
                this.score = 5 ;
            }else{
                this.score  = 1 ;
                this.isSpecialFood = false ;
            }
            this.position = new Point2D(rn.nextInt(Platform.WIDTH), rn.nextInt(Platform.HEIGHT));
        }while (prev_position == this.position);
    }

    public Point2D getPosition() {
        return this.position ;
    }

    public int getScore() {
        return this.score;
    }
}
@Test
    public void scoreShouldBeIncreasedByFiveWhenSnakeEatsGreenFood() throws InvocationTargetException, IllegalAccessException{
        gameLoopUnderTest = new GameLoop(new Platform(), new Snake(new Point2D(0,0)), new Food(new Point2D(0,1),true));
        gameLoopUnderTest.getPlatform().setKey(KeyCode.DOWN);
        clockTickHelper();
        clockTickHelper();
        assertEquals(5,gameLoopUnderTest.getSnake().getSnakeScore());
    }
Icez — 06/10/2022 16:05
select vendor_id , Round(avg(invoice_total),2) as average_invoice_amount from invoices
group by vendor_id 
having avg(invoice_total) > 2000
order by average_invoice_amount DESC
ภาพ
ภาพ
ภาพ
Icez — 12/10/2022 15:06
https://discord.gg/agapagBn
Icez — 04/11/2022 8:30
ประเภทไฟล์ที่แนบ: acrobat
algorithmProject.pdf
183.83 KB
Icez — 15/11/2022 15:47
ภาพ
Icez — วันนี้ เวลา 11:36
https://discord.com/channels/@me/1027429957103800391/1050625063638011904
Markdown Cheatsheet<a name="TOP"></a>
===================

- - - - 
# Heading 1 #

    Markup :  # Heading 1 #

    -OR-

    Markup :  ============= (below H1 text)

## Heading 2 ##

    Markup :  ## Heading 2 ##

    -OR-

    Markup: --------------- (below H2 text)

### Heading 3 ###

    Markup :  ### Heading 3 ###

Common text

    Markup :  Common text

_Emphasized text_

    Markup :  _Emphasized text_ or *Emphasized text*

~~Strikethrough text~~

    Markup :  ~~Strikethrough text~~

__Strong text__

    Markup :  __Strong text__ or **Strong text**

___Strong emphasized text___

    Markup :  ___Strong emphasized text___ or ***Strong emphasized text***

[Named Link](http://www.google.fr/ "Named link title") and http://www.google.fr/ or <http://example.com/>

    Markup :  [Named Link](http://www.google.fr/ "Named link title") and http://www.google.fr/ or <http://example.com/>

[heading-1](#heading-1 "Goto heading-1")
    
    Markup: [heading-1](#heading-1 "Goto heading-1")

Table, like this one :

First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell

```
First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell
```

`code()`

    Markup :  `code()`

```javascript
    var specificLanguage_code = 
    {
        "data": {
            "lookedUpPlatform": 1,
            "query": "Kasabian+Test+Transmission",
            "lookedUpItem": {
                "name": "Test Transmission",
                "artist": "Kasabian",
                "album": "Kasabian",
                "picture": null,
                "link": "http://open.spotify.com/track/5jhJur5n4fasblLSCOcrTp"
            }
        }
    }
```

    Markup : ```javascript
             ```

* Bullet list
    * Nested bullet
        * Sub-nested bullet etc
* Bullet list item 2

1. A numbered list
    1. A nested numbered list
    2. Which is numbered
2. Which is numbered

... (57 บรรทัด)
ย่อ
README.md
4 KB
﻿
Markdown Cheatsheet<a name="TOP"></a>
===================

- - - - 
# Heading 1 #

    Markup :  # Heading 1 #

    -OR-

    Markup :  ============= (below H1 text)

## Heading 2 ##

    Markup :  ## Heading 2 ##

    -OR-

    Markup: --------------- (below H2 text)

### Heading 3 ###

    Markup :  ### Heading 3 ###

Common text

    Markup :  Common text

_Emphasized text_

    Markup :  _Emphasized text_ or *Emphasized text*

~~Strikethrough text~~

    Markup :  ~~Strikethrough text~~

__Strong text__

    Markup :  __Strong text__ or **Strong text**

___Strong emphasized text___

    Markup :  ___Strong emphasized text___ or ***Strong emphasized text***

[Named Link](http://www.google.fr/ "Named link title") and http://www.google.fr/ or <http://example.com/>

    Markup :  [Named Link](http://www.google.fr/ "Named link title") and http://www.google.fr/ or <http://example.com/>

[heading-1](#heading-1 "Goto heading-1")
    
    Markup: [heading-1](#heading-1 "Goto heading-1")

Table, like this one :

First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell

```
First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell
```

`code()`

    Markup :  `code()`

```javascript
    var specificLanguage_code = 
    {
        "data": {
            "lookedUpPlatform": 1,
            "query": "Kasabian+Test+Transmission",
            "lookedUpItem": {
                "name": "Test Transmission",
                "artist": "Kasabian",
                "album": "Kasabian",
                "picture": null,
                "link": "http://open.spotify.com/track/5jhJur5n4fasblLSCOcrTp"
            }
        }
    }
```

    Markup : ```javascript
             ```

* Bullet list
    * Nested bullet
        * Sub-nested bullet etc
* Bullet list item 2

1. A numbered list
    1. A nested numbered list
    2. Which is numbered
2. Which is numbered

- [ ] An uncompleted task
- [x] A completed task

Foldable text:

<details>
  <summary>Title 1</summary>
  <p>Content 1 Content 1 Content 1 Content 1 Content 1</p>
</details>
<details>
  <summary>Title 2</summary>
  <p>Content 2 Content 2 Content 2 Content 2 Content 2</p>
</details>

```html
<h3>HTML</h3>
<p> Some HTML code here </p>
```

Link to a specific part of the page:

[Go To TOP](#TOP)

Hotkey:

<kbd>⌘F</kbd>

<kbd>⇧⌘F</kbd>

    Markup : <kbd>⌘F</kbd>

Hotkey list:

| Key | Symbol |
| --- | --- |
| Option | ⌥ |
| Control | ⌃ |
| Command | ⌘ |
| Shift | ⇧ |
| Caps Lock | ⇪ |
| Tab | ⇥ |
| Esc | ⎋ |
| Power | ⌽ |
| Return | ↩ |
| Delete | ⌫ |
| Up | ↑ |
| Down | ↓ |
| Left | ← |
| Right | → |

Emoji:

:exclamation: Use emoji icons to enhance text. :+1:  Look up emoji codes at [emoji-cheat-sheet.com](http://emoji-cheat-sheet.com/)

    Markup : Code appears between colons :EMOJICODE:

:mask: