# **Docker安装Odoo** #
## 服务简介 ##

<img src="./../images/odoo.png" width = "420" alt="Github" align=center />

* * *

Odoo最初的名字为TinyERP，08年5月之后称之为改名OpenERP之后又改为Odoo是一套全球开源的ERP/CRM系统。Odoo 是用于经营公司很好的开源管理软件。     

Odoo是一系列开源商业应用套件，此套件可满足公司的大部分应用需求，例如，企业基本的进销存、采购、销售、MRP生产制造、预算管理、WMS仓库库存管理、企业招聘、员工合同、休假、午餐管理、条码、商店、论坛、车队管理、客户追溯管理、VOIP、网店、企业官方网站，财务会计、E-Shop电子商务、银行对账、CRM客户关系管理、资产管理、HR工资管理、POS餐饮、项目管理、聊天IM沟通、PLM等等。        

Odoo是使用Python语言开发，开源协议已由 AGPL 转变为 LGPL v3，数据库采用开源的PostgreSQL，系统以AGPL协议发布。

Odoo系统提供较灵活的模块架构，常用模块包括：客户关系管理、库存管理、采购管理、生产管理、财务管理、销售管理、货品管理、营销管理、人事管理、服务支持等等。

Open 很有创新的项目是 OpenObject, 它是一个基于 Python 的企业应用快速开发框架， 这可能是Open ERP最吸引人和最大的亮点。

用户可以直接从模块库中选择安装适用模块，或进行模块卸载，升级的管理操作。

客户端用户界面是基于GTK+的，同时支持Linux和Windows平台。目前还有基于 TurboGears的eTiny Web客户端。

服务端的 Web Services 设计， 使其支持 SOAP, XML-RPC, NET-RPC ， 这样未来能更好的支持 SOA 体系结构。服务端工作流引擎的提供使其未来对BPM的支持有更多的期待.      

基于XML-PRC的接口，易于开发与定制，目前有基于Ajax的web界面，可与其他项目如Joomla，OsCommerce，Office等方便集成

集成Request Tracker, 功能类似于Perl 著名项目RT，使业务及相关事务的跟踪服务管理更为出色。


 <img src="https://github.com/favicon.ico" width = "20" alt="Github" align=center />

[ GitHub ](https://github.com/odoo/odoo)
## 准备镜像 ##
    docker pull odoo
## 运行容器 ##
#### 参数说明 ####