# 07.03.24 am

### vw und vh

- vw und vh bezeihen sich au f den viewport (browsergröße, -höhe)(sichtbarer bereich im browser genauer gesagt weil man ja z.b. an der seite auch noch dev mode aufhaben könnte)
- vw (viewport width): breite des angezeigten dokuments in prozent-anteil von dem viewport<br>z.b. 50px 50% des viewports
- % an sich bezieht sich auf das elternelement (positioning oder flexbos..)

### rem und em

- in root-element `:root{}` font-size definieren (standard 16px)<br>font-size: 2rem für ein element hieße dann
- em bezieht sich auf elternelement

### media queries

- ab einer bestimmten min-width beispielsweise aber einer bestimmten weite soll sich etwas anders verhalten.
- man fängt bei mobile an (design für smartphone). ist zwar herausfordernder am smartphone alles auf der kleinen fläche darzustellen, dafür danach einfacher auf der größeren fläche. außerdem viel genutzt.
- jeweils immer in der css-datei in der auch die betroffenen classes sind. auch wenn dann quais gleicher media query in mehreren dateien ist.
- wie kommt man auf die pixel-werte? wo sind die break points zwischen größe von smartphone - tablet - .. -> es gibt keine richtigen standards, man muss es selber ausprobieren, weil es so viele unterschiedliche display-größen gibt
