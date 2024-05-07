### Flash模块<!-- {docsify-ignore} -->

1. #### FLASH读数据

![image-20230427175930800](Flash.assets/image-20230427175930800.png) 

```c#
flash.readUChar(0)
```



2. #### FLASH写数据

![image-20230427175944518](Flash.assets/image-20230427175944518.png) 

```c#
flash.writeUChar(0,buf,0);
```



3. #### FLASH全部擦除

![image-20230427175958871](Flash.assets/image-20230427175958871.png) 

```c#
flash.FLASH_ErasePageALL(); //擦除 flash 全部数据
```

