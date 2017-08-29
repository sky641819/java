utocmd! bufwritepost _vimrc source % " vimrc文件修改之后自动加载。 windows。  
autocmd! bufwritepost .vimrc source % " vimrc文件修改之后自动加载。 linux。  
  
    
    " 自动完成   
    set completeopt=longest,menu  
    " 增强模式中的命令行自动完成操作  
    set wildmenu  
    " Ignore compiled files  
    set wildignore=*.o,*~,*.pyc  
      
      " Python 文件的一般设置，比如不要 tab 等  
      autocmd FileType python set tabstop=4 shiftwidth=4 expandtab  
      "自动补全配置  
      autocmd FileType python set omnifunc=pythoncomplete#Complete  
        
          
          " Return to last edit position when opening files (You want this!)  
          autocmd BufReadPost *  
               \ if line("'\"") > 0 && line("'\"") <= line("$") |  
                    \   exe "normal! g`\"" |  
                         \ endif  
                           
                           " A buffer becomes hidden when it is abandoned  
                           "set hid  
                             
                             " For regular expressions turn magic on  
                             set magic  
                               
                               " Configure backspace so it acts as it should act  
                               set backspace=eol,start,indent  
                               set whichwrap+=<,>,h,l  
                                 
                                 "pydiction 1.2 python auto complete  
                                 let g:pydiction_location = '~/.vim/tools/pydiction/complete-dict'  
                                 "defalut g:pydiction_menu_height == 15  
                                 let g:pydiction_menu_height = 20   
