<?php

if(count($_POST) > 0):


// nhan thong tin tu form
    $email = $_POST['email'];
    $pwd = $_POST['password'];

    $user = new \assignment1\User();
    $user = $user->attempt($email,$pwd);
    if(!is_null($user)){
        $_SESSION['user']= $user;
        header("Location: ?route=users");
    }else{
        header("Location: ?route=login");
    }

endif;