F5 WAF (LTM+ASM) AUTO SCALING用テンプレートのデプロイ
===================================================

このソリューションは、自動スケーリング用に構成されたMicrosoft Azure VMスケールセットにARMテンプレートを使用して、F5 BIG-IP LTM + ASM仮想版 (Virtual Edition) インスタンスの展開を実施します。 トラフィックは、AzureロードバランサからBIG-IP VE (クラスタ) に、次にアプリケーションサーバに流れます。 BIG-IP VEはシングル NIC モードで構成されています。 トラフィックが増加または減少するにつれて BIG-IP VE LTMインスタンスの数が自動的に増減します。 スケーリングのしきい値は現在、ネットワーク出力スループットに基づいています。 このソリューションは、BIG-IP LTM + ASM向けです。



.. toctree::
   :maxdepth: 1
   :glob:

   deploy
   confirm1
   confirm2
   confirm3