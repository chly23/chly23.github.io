---
title: PHP convert string to utf8
date: 2016-03-15 16:08:45
tags: php
categories: php
---
    public function convertStringToUtf8($string)
    {
        $string = urldecode($string);
        $encoding = mb_detect_encoding($string, array('ASCII', 'UTF-8', 'GB2312', 'GBK', 'BIG5'));
        $string = mb_convert_encoding($string, 'UTF-8', $encoding);
        $string = trim(str_replace('GB2312', 'utf-8', $string));//换xml类型编码
        return $string;
    }

