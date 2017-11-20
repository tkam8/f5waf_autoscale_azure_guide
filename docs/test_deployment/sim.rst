.. _module1:

SQL インジェクション攻撃のシミュレーション
====================================================

ASM のセキュリティポリシー内に準備されている SQL インジェクション攻撃用のシグネチャに対する攻撃を試行して下さい。 


   |sql_1|

#. 例えば WordPress の検索フォームに ' && 1 --　と入力し SQL インジェクション攻撃を試みると
   BIG-IP WAF (AFM) が攻撃ブロックすることが確認出来ます。
   
   |sql_2|
   
#. F5 WAF (ASM) がリクエストをブロックしたことを示すページが表示されます。 

   |sql_3|
   
#. F5 WAF の Event Logs に攻撃の詳細が表示されます。外部ログサーバーに送信するよう設定することも可能です。

   |sql_4|
   
   
.. |sql_1| image:: images/sql_1.png
.. |sql_2| image:: images/sql_2.png   
.. |sql_3| image:: images/sql_3.png
.. |sql_4| image:: images/sql_4.png