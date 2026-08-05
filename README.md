# ABAP_XJ
SAP-AI
1.	总体介绍

1.1.	本文档的目的
本文档的目的是规范森大国际系统项目的开发标准，提高代码质量，并且作为之后系统维护的依据和参照。就将来森大国际SAP系统进一步的升级和扩展，本文档也可作为参照的规范蓝本。
1.2.	公共标识符  
一些公共标识符用在程序命名标准中。公共标识符以及它所附带地有效的值将在以下中被规定。如果在命名程序中要用到公共标识符请在本章节中查找。
1.3.	功能的应用区
功能区 	功能代码
物料管理	MM
生产计划	PP
销售与分销	SD
财务会计	FI
管理会计	CO
仓库管理	WM
全面预算	BPC
1.4.	程序类型 
程序类型	标识符
报表(Report)	R
接口(Interface)	I
事务(Transaction)	T
表单(Form)	F
增强(Enhancement)	E
打印(Smartforms)	S
1.5.	接口系统代号
系统名称	标识符
	
	
	
1.6.	命名规范
这一部分主要是对森大国际SAP系统的软件开发（包括报表开发）程序命名规范的说明。利用本规范可以使程序更加可读，便于以后的维护与支持。
1.7.	ABAP/4 程序说明 
1.8.	程序命名 

程序分类	说明
1. 可执行程序	7个字符
程序名以Z开头，然后是2位应用模块的代号，然后紧接的是程序类型，然后是3位的程序编号。如: ZFIR002
2. 复制SAP或者定制的程序	复制SAP的程序的前缀为Z
3. 独立的Includes程序	Includes程序以Z开头，紧跟IN然后是程序说明。 
如Z_IN_CONSTANT
4. 事务程序中的include程序	接着事务程序的名字之后定义4个字符, 如：
ZFIR002_TOP  全局参数
ZFIR002_I01  PAI池
ZFIR002_O01 PBO池
ZFIR002_F01  子程序池

1.9.	变量命名协议
         不要用数据库的字段命名，因为它的值可能会在ABAP中改变。 所有的文件名字必须是英文，而且尽可能的描述它的作用或者内容，在名字中不要出现连字号。
1.9.1.	一般变量
Form
	FORM   Frm_get_cell.
ENDFORM.
Constant	C_<C>，<C>为描述
Variable	V_<C>，<C>为描述
Parameters	P_<C>，<C>为描述
参数－单选按钮
Parameter - radio button	P_RB_<C>，<C>为描述
参数－多选按钮
Parameter – checkbox	P_CB_<C>，<C>为描述
Field Symbols
字段符号	FS_<C>，<C>为描述
Select option
选择项	S_<C>，<C>为描述
Range	R_<C>，<C>为描述
Internal table
内表	IT_<C>，<C>为描述
Work area for itab 
工作区	WA_<C>，<C>为描述
Global 
全局变量	G_<C>，<C>为描述
Parameter of form
Form参数	PR_<C>，<C>为通过参考进行的描述。
PV_<C>，<C>为通过确切值进行的描述。
除BDC/公共FORM以外。
Types	TYP_<C>，<C>为描述
1.9.2.	模块池细节
Screen No.
屏幕号	4个字符，要求在9000－9999之间，屏幕增量为100。
GUI Status	NNNN_XXXXXXXX  13个字符，前4个为字符屏幕号，后8个字符代表描述。
PBO/PAI modules	XXXX_YYY_<C> X为屏幕号，Y为PBO/PAI，C为描述。
Area Menu
区域菜单	4个字符，Z<C>，<C>为描述
Logical Database
逻辑数据库	8个字符，Z<F><C>，F为功能区域，C为描述
Memory Id
存储器地址	PID_<C>，C为描述
Special Variables
特殊变量	OK_CODE
SAVE_OK
Text Element	text-001
Color 
颜色	COL_NORMAL
Transaction Code
事务代码	5个字符，Z<FF><NNN>，NN为3个数字。
1.9.3.	数据字典 
Table View
表格的视图	10个字符，以ZV开头，ZV_<C>，C为描述。
Tables
表格	4－10个字符，以ZT开头，ZT<C>，C为描述。
Table Index
表格索引	3个字符，以Z 开头，Z<NN>。<NN>为数字。
Structure
结构	ZS<C>，C为描述。
Fields	5～10个字符
Domains
域	10个字符，ZD_<C>，C为描述。
Data elements
数据要素	10个字符，ZE_<C>，C为描述。
Lock Objects	10个字符，EZ_<M>，M为对象名。
Type Group
类型组	5个字符，Z<FF><NN>，<FF>表示为功能模块，<NN>为数字。
Search help - Elementary/Collective	30个字符，Z _<FF>_<C>，<FF>表示为功能模块，C为3位编号。
1.9.4.	ABAP 询问  
User Group
用户组	12个字符，Z_<C>，C 为描述。
Function area	10个字符，Z_<C>，C为描述。
Query Name/ID
	14个字符，Z_<C>， C为描述。

1.9.5.	SAP对象脚本 
Layout set
版面设计	16个字符，Z<C>，C为描述。
Styles
字体	8个字符，Z<C>，C为描述。
Standard text Ids
标准文本的标识	4个字符，Z<C>，C为描述。
Standard text names
标准文本的名字	32个字符，Z<C>，C为描述。
SET/GET Parameters
建立/获取参数	3个字符，Z<C>，C为描述。
Number Range Objects	10个字符，Z<C>，C为描述。
Workflow Object Types
	10个字符，Z<C>，C为描述。
Message Id	4个字符，Z<C>，C为描述。
1.9.6.	批数据的通信
Batch Input Session	40个字符，ABAP程序名，加上4个字符的序列号。
Batch Job name
	和程序的名字相同
1.9.7.	程序属性 
Type
类型	T_<C>  
<C>为描述
Status
状态	SAP提供的标准
Application
应用程序	SAP提供的标准
Class
开发类	ZDEV   代表森大国际SAP系统
Function Groups	ZFG_<C>，<C>为描述
Message Class	ZDEVMSG
Authorization Group	必须是在开发过程中被核准的与可鉴别的。
Authorization Objects	
1.9.8.	工作台组织
你必须分配每一个自定义的开发工作一个任务，并依次分配给它们一个请求。这是在SAP系统中唯一的使源代码或者对象从一个实例转移到另外一个实例的方法。
所有为生产系统开发的程序必须被指派一个开发类和一个任务。除非是一个显示本地私人的、不可传输的$TMP。尽量把所有相关联的对象都放到共同的任务中去，也就是说任何的约束程序的要素，如ABAPs，定制表格，匹配代码，错误消息，数据字典对象等等都应该被指派一个相同的任务。这为防止对象不能获取或丢失传送进程而服务。同样的，为防止在移动更高级别的对象（如表）之前先移动了低级别的对象（如数据元素），SAP在一个任务中把所有的对象都进行了分类。
1.9.9.	编码规范
所有程序文档必须语言通达且可维护。所有程序注释应当描述功能模块的意图，不要重复描述程序逻辑。作为模块化考虑，编码需尽量分割成小的功能模块并为每个模块编写注释。对于FORM和程序块的抬头需加入至少两行注释。
1.9.10.	程序抬头
•	所有程序必须利用程序抬头作为程序的模版，并维护程序被更改与维护的历史。
       
1.9.11.	程序模块
大型的或综合的模块应当在模块前使用注释段，注释段模版如下：

**************************************************************************************
*   Comment
**************************************************************************************
 
1.9.12.	即时文档
•	随时使用即时注释来帮助读者理解特别的逻辑流程。

•	对于需要特别加以解释的声明或命令，请用“*”号整行注释。

•	对于变量和数据需要单独进行注释，用双引号做单行注释。


1.10.	程序开发指南
文档的这一部分给出了大致上的ABAP开发规范。
1.10.1.	大致规则
•	在新建ABAP程序前，必须检查是否存在现有程序可以作为一类特殊逻辑程序的模版。

•	SAP提供的专门为BDC的INCLUDE文件——BDCRECXY程序。

•	常用的常量声明要放到公用的Include程序（Z_IN_CONSTANT_4）中去。使用Text elements写入消息，这样可以让同样的程序在多语言系统中使用，无论何时尽量使用系统值。

•	尽量用LIKE声明数据，这样维护了此类变量的一致性。

•	检查所有的程序中的调试代码和break-point，在程序导入生产环境前确信测试编码（比如额外输出）被移除。在执行时设置“软断点”，不要在程序中硬录入它们。

•	每一回声明变量时应提供文字描述。

•	出于易读性考虑，ABAP应当保持段落缩进。命令“PRETTY PRINTER”应该被用来当作整理嵌套语句的工具。

•	权限检查必须被整合进所有开发的程序中。权限检查的需求必须被开发组明确表达且写入开发规范文档。

•	在维护阶段和测试后期阶段，不要删除无效的代码，把旧代码注释掉，新代码在下面写出。

•	不要使用ABAP关键字作为变量，这会让你的程序不稳定。

1.10.2.	模块化
•	出于可读性和逻辑清晰考虑请尽量使用子程序和Perform段。

•	在ABAP中多次使用的程序段落应该使用FORM。

1.10.3.	选项屏幕
•	Parameters 和 Select options 需要有一些默认值和强制输入项，可以提高程序执行效率。

•	更多使用Select options使过滤手段增加，程序运行加快。

•	所有输入值必须做检查，适当安排报错信息。

1.10.4.	数据库访问

•	在ABAP程序中绝对禁止直接访问数据库(EXEC SQL … END-EXEC)。这会绕过SAP数据字典检查并破坏系统完整。

•	出于性能考虑，不要使用逻辑数据库。访问逻辑数据库的运算量会给程序运行表现带来负面影响。

•	在每一次访问内表后，当访问成功时应该检查返回码（sy-subrc），如果没有纪录被返回，应报出适当的信息。

•	SAP数据库表必须通过SAP提供的代码以确认数据完整性。可以通过使用SAP现有程序或使用BDC跑屏方式。

•	外部结构须在数据字典中作为结构定义，这会简化维护流程尤其是同样的外部结构用在很多程序的情况下。

1.10.5.	WHERE 语句

•	SELECT语句完全可以使用WHERE选项，包括不属于这部分键值的fields。

•	WHERE条件的排列方式应该匹配内表中键值的排列方式。

•	EQ已经被证明比“=”号更高效。

•	无论何时不要在SELECT语句中采用负逻辑。

•	尽量使用主键值，建议使用全表的键值或者采用“SELECT SINGLE”用法。

•	如果可能用到次级索引的话，在WHERE语句中索引字段会依次列入清单并且用“AND”逻辑做出比较。

1.10.6.	内表
•	为了使程序更易读，重复的命令应该用冒号开头并联接起来，比如MOVE或WRITE语句。各自的关联对象应该被锯齿状缩进。

•	不要用COMPUTE指令，更多的用ADD, SUBTRACT, MULTIPLY, or DIVIDE指令。

•	当直接从数据库摘录数据到内表时，使用LIKE选项来确认变量采用同一特性。

•	尽量使用CASE语句代替重复的IF语句。

•	STOP和CHECK命令不要用在程序中，可是EXIT可以被用来离开LOOP。但是CHECK可以被用来在数据库选择中。

•	避免使用MOVE – CORRESPONDING，但是当内表结构完全一样的时候可以使用。

•	READ TABLE可以用键值搜索但BINARY SEARCH使用起来会有更好的性能，

•	使用CLEAR语句初始化内表的Work-Area。
•	SORT <itab> ORDER BY 比SORT ITAB性能优越。
•	使用REFRESH语句删除表内容，释放所有页空间。
•	如果程序中不在需要某个内表，使用FREE语句去删除表来释放所有分配的系统资源。
1.10.7.	模块池
•	使用ABAP工作台（SE80）建立维护所有模块池程序。这确保系统自动产生合适的程序结构包括其中的屏幕处理逻辑。所有的全局数据声明放在顶层include中。

•	在模块池中初始屏幕编号应为100，屏幕增量应为100，如果程序从标准程序中拷贝来那么增量应为9000到9999。

•	所有屏幕录入变量除了radio-buttons, push-buttons和check-boxes其他都需要用相关数据字典定义。这确保了变量的帮助信息可用，不要在屏幕上建立push-buttons，用Menu Painter代替。

•	用户定义菜单必须包含所有事务需要的动作。屏幕输出时的无效项必须隐藏掉。常用选项可以在菜单栏下面用Push Buttons实现。

1.11.	性能考量
•	请尽量避免使用select option 来耗费CPU利用率。尽量使用WHERE语句去代替。

•	更新并删除记录时，与其用SELECT … ENDSELECT结构，不如用UPDATE/DELETE来代替。

•	进行ABAP Report时，如果您使用了INSERT, UPDATE, 或 DELETE命令，请用COMMIT WORK语句来确认逻辑功能成功。因为系统会通过回滚功能来跟踪数据库内表变动（为了在最后确认前对所有改变进行确认），所以不使用COMMIT的话会引起数据瓶颈。

•	如果你想移动一个内表的所有项到另一个内表，且他们有相同的结构，你可以通过一下方法：
ITAB2[] = ITAB1[]
•	如果你想追加记录从一个内表到另一个内表，且他们有相同的结构，你可以通过一下方法：
APPEND LINES OF ITAB1 TO ITAB2.

•	LOOP … WHERE …比“LOOP整个表，然后通过CHECK检查条件”要快。

•	如果你需要选择语句，请用 “COLLECT statement”。

•	所有的LOOPS, IFs , CASEs和相似的声明应被分解为最简单的形式和不复杂的嵌套（除非完全有必要）。

•	选择WHILE 或 DO 时，首选WHILE。

•	所有的“CASE statements”必须有“WHEN OTHERS statement”来捕获不希望的错误。

•	只要有可能就要用CHECK 命令来代替IF，这样可以减少处理时间和改善可读性。

•	一旦指定的条件出现，就用EXIT 命令离开循环结构。

•	利用内表比利用字段组更能提高效率。

•	当要在内表中增加数据时，用“APPEND statement” 代替“COLLECT statement where”。这样可以通过避免比较现有数据从而提高运行速度。

•	避免使用“MOVE-CORRESPONDING”，这样可以通过避免比较历史结构从而提高运行速度。

•	当利用“CASE statements”时，应该按照出现机率的大小依次放到第一个case，第二个case等等。

•	在用“READ TABLE WITH KEY BINARY SEARCH”中，先把表格按照容易寻找的记录目标排列起来。

•	要使用可行的合乎逻辑的表达式，尽量避免用IN ，而要用EQ。

•	评价逻辑数据库的使用方法。有些时候它能减少程序运行时间，同时也有可能增加运行时间。这种影响是被程序选择的目标表的级别所决定的。

•	避免用“PERFORMS”调用外部程序的“FORMs”。

•	实时轨迹分析 (transaction SE30)被用来评估CPU和数据库表的存储性能。

•	扩展增强检查应该在传送程序之前被执行和评估。

•	在字符对比时用特殊的操作符如CO、CA 。特别的在长串比对中，每个字符的ABAP语句都能引起高的CPU的占有率。

•	要使程序中两个串相连，用“CONCATENATE”语句。同时，用“SPLIT”语句或者“STRLEN”功能来分拆一个串为几个部分或者决定每个串的长度。

•	如果你想删除在一个串中的第一行空格，用ABAP语法“SHIFT … LEFT DELETING LEADING …”，避免在 WHILE 循环中用“SHIFT”。

•	如果你想用一个与原字段类型不同的值（如初始值为“*********”）去初始化一个字段，用CLEAR <field> with <value>。

1.12.	加锁与解锁功能 
所有被开发者定制的透明的表格必须有一个Lock Object，它被手工创建目的是使加锁和解锁功能可用。
ENQUEUE功能锁定记录。锁定记录的目的是标记它，让你的程序在运行时不能被其他任何人所修改。例如：当你运行事务F-53 时，计算机运行“ENQUEUE_EFLFB1A.”锁定 the vendor 记录。

You can lock this record in your program by calling:
CALL FUNCTION ‘ENQUEUE_EFLFB1A’
EXPORTING
LIFNR = RF05A-AGKOK
BUKRS = RF05A-AGBUK
EXCEPTIONS
FOREIGN_LOCK = 01
SYSTEM_FAILURE = 02.

You unlock this record thus:
DATA ENQEBELN LIKE EKKO-EBELN.

CALL FUNCTION ‘DEQUEUE_EMEKKOE’
EXPORTING
EBELN       = ENQEBELN.
CLEAR ENQEBELN.

1.12.1.	规则：当你锁定记录
     如果你仅仅是涉及了表格，例如在表BKPF中查询会计凭证，你没有必要去锁定你正在查询的表。但是如果你要刷新你所询问的表格，你必须锁定这个及和它有关的表格。

1.12.2.	 对add-on table 操作
对add-on table 操作有必要用Enqueue and Dequeue。

1.12.3.	错误消息的处理
所有的错误消息都要通过标准格式的文件进行处理。“Error Description”应该尽可能的描述清楚且便于理解。
1.13.	传输请求号命名 
1.13.1.	规则
传输请求描述
如：SD_001-CAR系统POS零售销售处理_徐永平_20171206
其中SD_001就是开发清单中的需求编号,该程序的描述为‘CAR系统POS零售销售处理’，后面是开发人员的姓名及日期。
2.	程序变更 
在标准的SAP ABAP程序规定中，程序一般不修改的。如果变更一定而且彻底有必要，要详细的分析和回顾检查这次的修改与以后释放的牵连。程序列出文档向特定的定制ABAP程序和用户出口提出申请。
必须在修改的程序中的抬头文中加入修改记录。
在实际修改的代码中，应该加入修改目的，数字，最初的注释。在修改的新行代码中，程序initials 和时间的注释用“。不要从源程序中删除任何代码。被修改的代码不再被用，增加和删除部分用*注释。
因为主要的程序代码被重写，脱离原代码保留原来的注释，这样会干预到程序的可读性，删除代码和相应的注释。在更改历史记录的描述中要记录主要程序被重写和不可执行的代码被删除。

