## 结论
1. 源文件夹中嵌套的所有文件夹与文件，均会被**全部复制**到目标文件夹中
2. 对于同路径同名文件，源文件的文件会**替换**目标文件夹中
3. 目标文件夹中原本已有的文件与文件夹（源文件夹中没有），**会保留**。
## 测试代码
```
    IF test THEN  
        DirCopy_0(enable := TRUE , pSrcDev := ADR('SrcDev'), pSrcDir := ADR('test'), pDestDev := ADR('DestDev'), pDestDir := ADR('test'), option := fiOVERWRITE );  
        IF DirCopy_0.status<> 65535 THEN  
            IF DirCopy_0.status= 0 THEN  
                test:=FALSE;  
            END_IF  
            END_IF  
    END_IF
```