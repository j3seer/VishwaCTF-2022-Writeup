# Challenge description

Simple Todo list website to manage your tasks. Use it wisely. https://t0-d0-l1st.vishwactf.com/

-----------------------------------------------------------

this challenge is all about the showsource class in the source code

```php
<?php

Class ShowSource{
    public function __toString()
    {
        return highlight_file($this->source, true);
    }
}

if(isset($_GET['source'])){
    $s = new ShowSource();
    $s->source = __FILE__;
    echo $s;
    exit;
}

$todos = [];

if(isset($_COOKIE['todos'])){
    $c = $_COOKIE['todos'];
    $h = substr($c, 0, 40);
    $m = substr($c, 40);
    if(sha1($m) === $h){
        $todos = unserialize($m);
    }
}

if(isset($_POST['text'])){
    $todo = $_POST['text'];
    $todos[] = $todo;
    $m = serialize($todos);
    $h = sha1($m);
    setcookie('todos', $h.$m);
    header('Location: '.$_SERVER['REQUEST_URI']);
    exit;
}
?>
```

we notice our cookie gets the serialized object and we can easily modify it to read other source code of flag.php

this is a small php script to craft a serialized object that calls showsource

![image](https://user-images.githubusercontent.com/58823465/159311878-95c0f58a-efb8-4081-b508-30ac76b34dc2.png)



submitting that in the cookie and we get our flag 


```Flag: VishwaCTF{t7e_f1a6_1s_1is73d}```
