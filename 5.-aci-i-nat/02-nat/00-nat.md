# NAT

Network Address Translation — механизм в хозяйстве совершенно необходимый уже с 1994-го года. Много сессий об него сломано и пакетов потеряно.  
Нужен он чаще всего для подключения вашей локальной сети к Интернету. Дело в том, что теоретически существует 255_255_255\*255=4 228 250 625. 4 миллиарда адресов. Даже если бы у каждого жителя планеты был всего один компьютер, адресов бы уже не хватало. А тут разве что утюги к Интернету не подключаются. Умные люди сообразили это ещё в начале 90-х и как временное решение предложили разделить пространство адресов на публичные \(белые\) и приватные \(частные, серые\).  
К последним относятся три диапазона:

10.0.0.0/8  
172.16.0.0/12  
192.168.0.0/16

Их вы свободно можете использовать в своей частной сети, и поэтому, разумеется, они будут повторяться. Как же быть с уникальностью? Кому будет отвечать WEB-сервер, которому пришёл запрос с обратным адресом 192.168.1.1? Ростелекому? Компании Татнефть? Или вашему комнатному Длинку? В большом интернете никто ничего не знает о приватных сетях — они не маршрутизируются.  
Тут и выходит на сцену NAT. По большому счёту, это обман, подстава. На натирующем устройстве ваш приватный адрес, грубо говоря, просто подменяется на белый адрес, который и будет фигурировать далее в пакете, пока он путешествует до WEB-сервера. А вот белые адреса очень даже хорошо маршрутизируются, и пакет точно вернётся обратно на натирующее устройство.  
Но как оно в свою очередь поймёт, что с ним делать дальше? Вот с этим и разберёмся.
