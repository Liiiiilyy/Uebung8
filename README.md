# java/Uebung8

## `abstract class Actor()`

- Erzeugt eine abstrakte Basisklasse `Actor`für alle Spielobjekte
- Die Klasse erbt von `GameObject`. Ihr Konstruktor soll dieselben Parameter haben wie der von GameObject, **zusätzlich einen Parameter für das Spielfeld (Klasse Field)**
- Konstruktor von `GameObject` : [see](https://github.com/Liiiiilyy/Uebung8/blob/6a9ddc213f506d01e5b511d8213957d5e65fd2fe/src/GameObject.java#L267)
    - super 相当于是指向当前对象的父类，这样就可以用 **super.xxx**
     来引用父类的成员。
        
        ```cpp
        super(x, y, rotation, fileName);
        				this.x = x;
                this.y = y;
                this.rotation = rotation & 3;
                setImage(fileName);
        ```
        
- Methode boolean `canWalk(int)`
    - 该方法用于确定`Actor`对象是否可以朝指定方向移动。
    - `hasNeighbor == true`  → can walk
- 此外，还应添加一个`abstract method void act()`，该方法在下两个任务中将被`overwrite`。
    - abstract method是写在base class中无需实现的method，在他的子类中需要`overwrite`。

## `class Player`

- 定义一个`class Player`，用于表示由玩家控制的角色。该class继承自`Actor`。
- 它的`Constructor`应该获取位置`int x, int y, rotation`和`field`，并将它们与固定的图形文件名一起传递给Actor的`Constructor`。
- `Override act()`，该方法将控制Player对象，因为`Player`也是`Actor`和`GameObject`。`act`方法将一直等待，直到`Player`执行有效的移动，即接受键盘输入。

## `class NPC`

- 让`class Walker` 继承`Actor`，并对其进行适当修改。由于它本身是一个`GameObject`，因此无需再远程控制其他对象，而是可以自己控制。
- 对Walker的改写为
    - walker直接继承自actor，walker也有actor的一些基本attribute
    - U6中是在constructor中定义一个`GameObject`  attribute完成的。

## 让所有`Actor`运动起来

- 将所有`Actor object`添加到一个`ArrayList`中（`Player obiect`）。在循环的主体中，只需要遍历`ArrayList`，并为每个条目调用act()方法即可使游戏运行。

011 +
