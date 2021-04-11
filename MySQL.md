

<h2><a id="user-content-基本语法" class="anchor" aria-hidden="true" href="#基本语法"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>基本语法</h2>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 显示所有数据库</span>
show databases;

<span class="pl-c"><span class="pl-c">--</span> 创建数据库</span>
<span class="pl-k">CREATE</span> <span class="pl-k">DATABASE</span> <span class="pl-en">test</span>;

<span class="pl-c"><span class="pl-c">--</span> 切换数据库</span>
use test;

<span class="pl-c"><span class="pl-c">--</span> 显示数据库中的所有表</span>
show tables;

<span class="pl-c"><span class="pl-c">--</span> 创建数据表</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">pet</span> (
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    owner <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    species <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    sex <span class="pl-k">CHAR</span>(<span class="pl-c1">1</span>),
    birth <span class="pl-k">DATE</span>,
    death <span class="pl-k">DATE</span>
);

<span class="pl-c"><span class="pl-c">--</span> 查看数据表结构</span>
<span class="pl-c"><span class="pl-c">--</span> describe pet;</span>
<span class="pl-k">desc</span> pet;

<span class="pl-c"><span class="pl-c">--</span> 查询表</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">from</span> pet;

<span class="pl-c"><span class="pl-c">--</span> 插入数据</span>
<span class="pl-k">INSERT INTO</span> pet <span class="pl-k">VALUES</span> (<span class="pl-s"><span class="pl-pds">'</span>puffball<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>Diane<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>hamster<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>f<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1990-03-30<span class="pl-pds">'</span></span>, <span class="pl-k">NULL</span>);

<span class="pl-c"><span class="pl-c">--</span> 修改数据</span>
<span class="pl-k">UPDATE</span> pet <span class="pl-k">SET</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>squirrel<span class="pl-pds">'</span></span> <span class="pl-k">where</span> owner <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>Diane<span class="pl-pds">'</span></span>;

<span class="pl-c"><span class="pl-c">--</span> 删除数据</span>
<span class="pl-k">DELETE</span> <span class="pl-k">FROM</span> pet <span class="pl-k">where</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>squirrel<span class="pl-pds">'</span></span>;

<span class="pl-c"><span class="pl-c">--</span> 删除表</span>
<span class="pl-k">DROP</span> <span class="pl-k">TABLE</span> myorder;</pre></div>
<h2><a id="user-content-建表约束" class="anchor" aria-hidden="true" href="#建表约束"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>建表约束</h2>
<h3><a id="user-content-主键约束" class="anchor" aria-hidden="true" href="#主键约束"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>主键约束</h3>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 主键约束</span>
<span class="pl-c"><span class="pl-c">--</span> 使某个字段不重复且不得为空，确保表内所有数据的唯一性。</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">user</span> (
    id <span class="pl-k">INT</span> <span class="pl-k">PRIMARY KEY</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>)
);

<span class="pl-c"><span class="pl-c">--</span> 联合主键</span>
<span class="pl-c"><span class="pl-c">--</span> 联合主键中的每个字段都不能为空，并且加起来不能和已设置的联合主键重复。</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">user</span> (
    id <span class="pl-k">INT</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    password <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    <span class="pl-k">PRIMARY KEY</span>(id, name)
);

<span class="pl-c"><span class="pl-c">--</span> 自增约束</span>
<span class="pl-c"><span class="pl-c">--</span> 自增约束的主键由系统自动递增分配。</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">user</span> (
    id <span class="pl-k">INT</span> <span class="pl-k">PRIMARY KEY</span> AUTO_INCREMENT,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>)
);

<span class="pl-c"><span class="pl-c">--</span> 添加主键约束</span>
<span class="pl-c"><span class="pl-c">--</span> 如果忘记设置主键，还可以通过SQL语句设置（两种方式）：</span>
<span class="pl-k">ALTER</span> <span class="pl-k">TABLE</span> user ADD <span class="pl-k">PRIMARY KEY</span>(id);
<span class="pl-k">ALTER</span> <span class="pl-k">TABLE</span> user MODIFY id <span class="pl-k">INT</span> <span class="pl-k">PRIMARY KEY</span>;

<span class="pl-c"><span class="pl-c">--</span> 删除主键</span>
<span class="pl-k">ALTER</span> <span class="pl-k">TABLE</span> user drop <span class="pl-k">PRIMARY KEY</span>;</pre></div>
<h3><a id="user-content-唯一主键" class="anchor" aria-hidden="true" href="#唯一主键"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>唯一主键</h3>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 建表时创建唯一主键</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">user</span> (
    id <span class="pl-k">INT</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    UNIQUE(name)
);

<span class="pl-c"><span class="pl-c">--</span> 添加唯一主键</span>
<span class="pl-c"><span class="pl-c">--</span> 如果建表时没有设置唯一建，还可以通过SQL语句设置（两种方式）：</span>
<span class="pl-k">ALTER</span> <span class="pl-k">TABLE</span> user ADD UNIQUE(name);
<span class="pl-k">ALTER</span> <span class="pl-k">TABLE</span> user MODIFY name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) UNIQUE;

<span class="pl-c"><span class="pl-c">--</span> 删除唯一主键</span>
<span class="pl-k">ALTER</span> <span class="pl-k">TABLE</span> user DROP INDEX name;</pre></div>
<h3><a id="user-content-非空约束" class="anchor" aria-hidden="true" href="#非空约束"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>非空约束</h3>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 建表时添加非空约束</span>
<span class="pl-c"><span class="pl-c">--</span> 约束某个字段不能为空</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">user</span> (
    id <span class="pl-k">INT</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-k">NOT NULL</span>
);

<span class="pl-c"><span class="pl-c">--</span> 移除非空约束</span>
<span class="pl-k">ALTER</span> <span class="pl-k">TABLE</span> user MODIFY name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>);</pre></div>
<h3><a id="user-content-默认约束" class="anchor" aria-hidden="true" href="#默认约束"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>默认约束</h3>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 建表时添加默认约束</span>
<span class="pl-c"><span class="pl-c">--</span> 约束某个字段的默认值</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">user2</span> (
    id <span class="pl-k">INT</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    age <span class="pl-k">INT</span> DEFAULT <span class="pl-c1">10</span>
);

<span class="pl-c"><span class="pl-c">--</span> 移除非空约束</span>
<span class="pl-k">ALTER</span> <span class="pl-k">TABLE</span> user MODIFY age <span class="pl-k">INT</span>;</pre></div>
<h3><a id="user-content-外键约束" class="anchor" aria-hidden="true" href="#外键约束"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>外键约束</h3>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 班级</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">classes</span> (
    id <span class="pl-k">INT</span> <span class="pl-k">PRIMARY KEY</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>)
);

<span class="pl-c"><span class="pl-c">--</span> 学生表</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">students</span> (
    id <span class="pl-k">INT</span> <span class="pl-k">PRIMARY KEY</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    <span class="pl-c"><span class="pl-c">--</span> 这里的 class_id 要和 classes 中的 id 字段相关联</span>
    class_id <span class="pl-k">INT</span>,
    <span class="pl-c"><span class="pl-c">--</span> 表示 class_id 的值必须来自于 classes 中的 id 字段值</span>
    <span class="pl-k">FOREIGN KEY</span>(class_id) <span class="pl-k">REFERENCES</span> classes(id)
);

<span class="pl-c"><span class="pl-c">--</span> 1. 主表（父表）classes 中没有的数据值，在副表（子表）students 中，是不可以使用的；</span>
<span class="pl-c"><span class="pl-c">--</span> 2. 主表中的记录被副表引用时，主表不可以被删除。</span></pre></div>
<h2><a id="user-content-数据库的三大设计范式" class="anchor" aria-hidden="true" href="#数据库的三大设计范式"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>数据库的三大设计范式</h2>
<h3><a id="user-content-1nf" class="anchor" aria-hidden="true" href="#1nf"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>1NF</h3>
<p>只要字段值还可以继续拆分，就不满足第一范式。</p>
<p>范式设计得越详细，对某些实际操作可能会更好，但并非都有好处，需要对项目的实际情况进行设定。</p>
<h3><a id="user-content-2nf" class="anchor" aria-hidden="true" href="#2nf"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2NF</h3>
<p>在满足第一范式的前提下，其他列都必须完全依赖于主键列。如果出现不完全依赖，只可能发生在联合主键的情况下：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 订单表</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">myorder</span> (
    product_id <span class="pl-k">INT</span>,
    customer_id <span class="pl-k">INT</span>,
    product_name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    customer_name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    <span class="pl-k">PRIMARY KEY</span> (product_id, customer_id)
);</pre></div>
<p>实际上，在这张订单表中，<code>product_name</code> 只依赖于 <code>product_id</code> ，<code>customer_name</code> 只依赖于 <code>customer_id</code> 。也就是说，<code>product_name</code> 和 <code>customer_id</code> 是没用关系的，<code>customer_name</code> 和 <code>product_id</code> 也是没有关系的。</p>
<p>这就不满足第二范式：其他列都必须完全依赖于主键列！</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">myorder</span> (
    order_id <span class="pl-k">INT</span> <span class="pl-k">PRIMARY KEY</span>,
    product_id <span class="pl-k">INT</span>,
    customer_id <span class="pl-k">INT</span>
);

<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">product</span> (
    id <span class="pl-k">INT</span> <span class="pl-k">PRIMARY KEY</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>)
);

<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">customer</span> (
    id <span class="pl-k">INT</span> <span class="pl-k">PRIMARY KEY</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>)
);</pre></div>
<p>拆分之后，<code>myorder</code> 表中的 <code>product_id</code> 和 <code>customer_id</code> 完全依赖于 <code>order_id</code> 主键，而 <code>product</code> 和 <code>customer</code> 表中的其他字段又完全依赖于主键。满足了第二范式的设计！</p>
<h3><a id="user-content-3nf" class="anchor" aria-hidden="true" href="#3nf"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>3NF</h3>
<p>在满足第二范式的前提下，除了主键列之外，其他列之间不能有传递依赖关系。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">myorder</span> (
    order_id <span class="pl-k">INT</span> <span class="pl-k">PRIMARY KEY</span>,
    product_id <span class="pl-k">INT</span>,
    customer_id <span class="pl-k">INT</span>,
    customer_phone <span class="pl-k">VARCHAR</span>(<span class="pl-c1">15</span>)
);</pre></div>
<p>表中的 <code>customer_phone</code> 有可能依赖于 <code>order_id</code> 、 <code>customer_id</code> 两列，也就不满足了第三范式的设计：其他列之间不能有传递依赖关系。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">myorder</span> (
    order_id <span class="pl-k">INT</span> <span class="pl-k">PRIMARY KEY</span>,
    product_id <span class="pl-k">INT</span>,
    customer_id <span class="pl-k">INT</span>
);

<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">customer</span> (
    id <span class="pl-k">INT</span> <span class="pl-k">PRIMARY KEY</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    phone <span class="pl-k">VARCHAR</span>(<span class="pl-c1">15</span>)
);</pre></div>
<p>修改后就不存在其他列之间的传递依赖关系，其他列都只依赖于主键列，满足了第三范式的设计！</p>
<h2><a id="user-content-查询练习" class="anchor" aria-hidden="true" href="#查询练习"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>查询练习</h2>
<h3><a id="user-content-准备数据" class="anchor" aria-hidden="true" href="#准备数据"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>准备数据</h3>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 创建数据库</span>
<span class="pl-k">CREATE</span> <span class="pl-k">DATABASE</span> <span class="pl-en">select_test</span>;
<span class="pl-c"><span class="pl-c">--</span> 切换数据库</span>
USE select_test;

<span class="pl-c"><span class="pl-c">--</span> 创建学生表</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">student</span> (
    no <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-k">PRIMARY KEY</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-k">NOT NULL</span>,
    sex <span class="pl-k">VARCHAR</span>(<span class="pl-c1">10</span>) <span class="pl-k">NOT NULL</span>,
    birthday <span class="pl-k">DATE</span>, <span class="pl-c"><span class="pl-c">--</span> 生日</span>
    class <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-c"><span class="pl-c">--</span> 所在班级</span>
);

<span class="pl-c"><span class="pl-c">--</span> 创建教师表</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">teacher</span> (
    no <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-k">PRIMARY KEY</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-k">NOT NULL</span>,
    sex <span class="pl-k">VARCHAR</span>(<span class="pl-c1">10</span>) <span class="pl-k">NOT NULL</span>,
    birthday <span class="pl-k">DATE</span>,
    profession <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-k">NOT NULL</span>, <span class="pl-c"><span class="pl-c">--</span> 职称</span>
    department <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-k">NOT NULL</span> <span class="pl-c"><span class="pl-c">--</span> 部门</span>
);

<span class="pl-c"><span class="pl-c">--</span> 创建课程表</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">course</span> (
    no <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-k">PRIMARY KEY</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-k">NOT NULL</span>,
    t_no <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-k">NOT NULL</span>, <span class="pl-c"><span class="pl-c">--</span> 教师编号</span>
    <span class="pl-c"><span class="pl-c">--</span> 表示该 tno 来自于 teacher 表中的 no 字段值</span>
    <span class="pl-k">FOREIGN KEY</span>(t_no) <span class="pl-k">REFERENCES</span> teacher(no) 
);

<span class="pl-c"><span class="pl-c">--</span> 成绩表</span>
<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">score</span> (
    s_no <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-k">NOT NULL</span>, <span class="pl-c"><span class="pl-c">--</span> 学生编号</span>
    c_no <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>) <span class="pl-k">NOT NULL</span>, <span class="pl-c"><span class="pl-c">--</span> 课程号</span>
    degree <span class="pl-k">DECIMAL</span>,	<span class="pl-c"><span class="pl-c">--</span> 成绩</span>
    <span class="pl-c"><span class="pl-c">--</span> 表示该 s_no, c_no 分别来自于 student, course 表中的 no 字段值</span>
    <span class="pl-k">FOREIGN KEY</span>(s_no) <span class="pl-k">REFERENCES</span> student(no),	
    <span class="pl-k">FOREIGN KEY</span>(c_no) <span class="pl-k">REFERENCES</span> course(no),
    <span class="pl-c"><span class="pl-c">--</span> 设置 s_no, c_no 为联合主键</span>
    <span class="pl-k">PRIMARY KEY</span>(s_no, c_no)
);

<span class="pl-c"><span class="pl-c">--</span> 查看所有表</span>
SHOW TABLES;

<span class="pl-c"><span class="pl-c">--</span> 添加学生表数据</span>
<span class="pl-k">INSERT INTO</span> student <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>101<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>曾华<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>男<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1977-09-01<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>95033<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> student <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>102<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>匡明<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>男<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1975-10-02<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>95031<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> student <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>103<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>王丽<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>女<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1976-01-23<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>95033<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> student <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>104<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>李军<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>男<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1976-02-20<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>95033<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> student <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>105<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>王芳<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>女<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1975-02-10<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>95031<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> student <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>106<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>陆军<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>男<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1974-06-03<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>95031<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> student <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>107<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>王尼玛<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>男<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1976-02-20<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>95033<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> student <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>108<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>张全蛋<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>男<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1975-02-10<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>95031<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> student <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>109<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>赵铁柱<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>男<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1974-06-03<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>95031<span class="pl-pds">'</span></span>);

<span class="pl-c"><span class="pl-c">--</span> 添加教师表数据</span>
<span class="pl-k">INSERT INTO</span> teacher <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>804<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>李诚<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>男<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1958-12-02<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>副教授<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>计算机系<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> teacher <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>856<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>张旭<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>男<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1969-03-12<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>讲师<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>电子工程系<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> teacher <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>825<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>王萍<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>女<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1972-05-05<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>助教<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>计算机系<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> teacher <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>831<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>刘冰<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>女<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>1977-08-14<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>助教<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>电子工程系<span class="pl-pds">'</span></span>);

<span class="pl-c"><span class="pl-c">--</span> 添加课程表数据</span>
<span class="pl-k">INSERT INTO</span> course <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>计算机导论<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>825<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> course <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>3-245<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>操作系统<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>804<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> course <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>6-166<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>数字电路<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>856<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> course <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>9-888<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>高等数学<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>831<span class="pl-pds">'</span></span>);

<span class="pl-c"><span class="pl-c">--</span> 添加添加成绩表数据</span>
<span class="pl-k">INSERT INTO</span> score <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>103<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>92<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> score <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>103<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>3-245<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>86<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> score <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>103<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>6-166<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>85<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> score <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>105<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>88<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> score <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>105<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>3-245<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>75<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> score <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>105<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>6-166<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>79<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> score <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>109<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>76<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> score <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>109<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>3-245<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>68<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> score <span class="pl-k">VALUES</span>(<span class="pl-s"><span class="pl-pds">'</span>109<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>6-166<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>81<span class="pl-pds">'</span></span>);

<span class="pl-c"><span class="pl-c">--</span> 查看表结构</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> course;
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score;
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> student;
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> teacher;</pre></div>
<h3><a id="user-content-1-到-10" class="anchor" aria-hidden="true" href="#1-到-10"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>1 到 10</h3>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 查询 student 表的所有行</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> student;

<span class="pl-c"><span class="pl-c">--</span> 查询 student 表中的 name、sex 和 class 字段的所有行</span>
<span class="pl-k">SELECT</span> name, sex, class <span class="pl-k">FROM</span> student;

<span class="pl-c"><span class="pl-c">--</span> 查询 teacher 表中不重复的 department 列</span>
<span class="pl-c"><span class="pl-c">--</span> department: 去重查询</span>
<span class="pl-k">SELECT DISTINCT</span> department <span class="pl-k">FROM</span> teacher;

<span class="pl-c"><span class="pl-c">--</span> 查询 score 表中成绩在60-80之间的所有行（区间查询和运算符查询）</span>
<span class="pl-c"><span class="pl-c">--</span> BETWEEN xx AND xx: 查询区间, AND 表示 "并且"</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> degree BETWEEN <span class="pl-c1">60</span> <span class="pl-k">AND</span> <span class="pl-c1">80</span>;
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> degree <span class="pl-k">&gt;</span> <span class="pl-c1">60</span> <span class="pl-k">AND</span> degree <span class="pl-k">&lt;</span> <span class="pl-c1">80</span>;

<span class="pl-c"><span class="pl-c">--</span> 查询 score 表中成绩为 85, 86 或 88 的行</span>
<span class="pl-c"><span class="pl-c">--</span> IN: 查询规定中的多个值</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> degree <span class="pl-k">IN</span> (<span class="pl-c1">85</span>, <span class="pl-c1">86</span>, <span class="pl-c1">88</span>);

<span class="pl-c"><span class="pl-c">--</span> 查询 student 表中 '95031' 班或性别为 '女' 的所有行</span>
<span class="pl-c"><span class="pl-c">--</span> or: 表示或者关系</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> class <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>95031<span class="pl-pds">'</span></span> <span class="pl-k">or</span> sex <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>女<span class="pl-pds">'</span></span>;

<span class="pl-c"><span class="pl-c">--</span> 以 class 降序的方式查询 student 表的所有行</span>
<span class="pl-c"><span class="pl-c">--</span> DESC: 降序，从高到低</span>
<span class="pl-c"><span class="pl-c">--</span> ASC（默认）: 升序，从低到高</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> student <span class="pl-k">ORDER BY</span> class <span class="pl-k">DESC</span>;
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> student <span class="pl-k">ORDER BY</span> class <span class="pl-k">ASC</span>;

<span class="pl-c"><span class="pl-c">--</span> 以 c_no 升序、degree 降序查询 score 表的所有行</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score <span class="pl-k">ORDER BY</span> c_no <span class="pl-k">ASC</span>, degree <span class="pl-k">DESC</span>;

<span class="pl-c"><span class="pl-c">--</span> 查询 "95031" 班的学生人数</span>
<span class="pl-c"><span class="pl-c">--</span> COUNT: 统计</span>
<span class="pl-k">SELECT</span> <span class="pl-c1">COUNT</span>(<span class="pl-k">*</span>) <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> class <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>95031<span class="pl-pds">'</span></span>;

<span class="pl-c"><span class="pl-c">--</span> 查询 score 表中的最高分的学生学号和课程编号（子查询或排序查询）。</span>
<span class="pl-c"><span class="pl-c">--</span> (SELECT MAX(degree) FROM score): 子查询，算出最高分</span>
<span class="pl-k">SELECT</span> s_no, c_no <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> degree <span class="pl-k">=</span> (<span class="pl-k">SELECT</span> <span class="pl-c1">MAX</span>(degree) <span class="pl-k">FROM</span> score);

<span class="pl-c"><span class="pl-c">--</span>  排序查询</span>
<span class="pl-c"><span class="pl-c">--</span> LIMIT r, n: 表示从第r行开始，查询n条数据</span>
<span class="pl-k">SELECT</span> s_no, c_no, degree <span class="pl-k">FROM</span> score <span class="pl-k">ORDER BY</span> degree <span class="pl-k">DESC</span> <span class="pl-k">LIMIT</span> <span class="pl-c1">0</span>, <span class="pl-c1">1</span>;</pre></div>
<h3><a id="user-content-分组计算平均成绩" class="anchor" aria-hidden="true" href="#分组计算平均成绩"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>分组计算平均成绩</h3>
<p><strong>查询每门课的平均成绩。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> AVG: 平均值</span>
<span class="pl-k">SELECT</span> <span class="pl-c1">AVG</span>(degree) <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> c_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span>;
<span class="pl-k">SELECT</span> <span class="pl-c1">AVG</span>(degree) <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> c_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>3-245<span class="pl-pds">'</span></span>;
<span class="pl-k">SELECT</span> <span class="pl-c1">AVG</span>(degree) <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> c_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>6-166<span class="pl-pds">'</span></span>;

<span class="pl-c"><span class="pl-c">--</span> GROUP BY: 分组查询</span>
<span class="pl-k">SELECT</span> c_no, <span class="pl-c1">AVG</span>(degree) <span class="pl-k">FROM</span> score <span class="pl-k">GROUP BY</span> c_no;</pre></div>
<h3><a id="user-content-分组条件与模糊查询" class="anchor" aria-hidden="true" href="#分组条件与模糊查询"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>分组条件与模糊查询</h3>
<p><strong>查询 <code>score</code> 表中至少有 2 名学生选修，并以 3 开头的课程的平均分数。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score;
<span class="pl-c"><span class="pl-c">--</span> c_no 课程编号</span>
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">92</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">86</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">85</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">88</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">75</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">79</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">68</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">81</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span></pre></div>
<p>分析表发现，至少有 2 名学生选修的课程是 <code>3-105</code> 、<code>3-245</code> 、<code>6-166</code> ，以 3 开头的课程是 <code>3-105</code> 、<code>3-245</code> 。也就是说，我们要查询所有 <code>3-105</code> 和 <code>3-245</code> 的 <code>degree</code> 平均分。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 首先把 c_no, AVG(degree) 通过分组查询出来</span>
<span class="pl-k">SELECT</span> c_no, <span class="pl-c1">AVG</span>(degree) <span class="pl-k">FROM</span> score <span class="pl-k">GROUP BY</span> c_no
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-------------+</span>
| c_no  | <span class="pl-c1">AVG</span>(degree) |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-------------+</span>
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">85</span>.<span class="pl-c1">3333</span> |
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">76</span>.<span class="pl-c1">3333</span> |
| <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">81</span>.<span class="pl-c1">6667</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-------------+</span>

<span class="pl-c"><span class="pl-c">--</span> 再查询出至少有 2 名学生选修的课程</span>
<span class="pl-c"><span class="pl-c">--</span> HAVING: 表示持有</span>
<span class="pl-k">HAVING</span> <span class="pl-c1">COUNT</span>(c_no) <span class="pl-k">&gt;=</span> <span class="pl-c1">2</span>

<span class="pl-c"><span class="pl-c">--</span> 并且是以 3 开头的课程</span>
<span class="pl-c"><span class="pl-c">--</span> LIKE 表示模糊查询，"%" 是一个通配符，匹配 "3" 后面的任意字符。</span>
<span class="pl-k">AND</span> c_no <span class="pl-k">LIKE</span> <span class="pl-s"><span class="pl-pds">'</span>3%<span class="pl-pds">'</span></span>;

<span class="pl-c"><span class="pl-c">--</span> 把前面的SQL语句拼接起来，</span>
<span class="pl-c"><span class="pl-c">--</span> 后面加上一个 COUNT(*)，表示将每个分组的个数也查询出来。</span>
<span class="pl-k">SELECT</span> c_no, <span class="pl-c1">AVG</span>(degree), <span class="pl-c1">COUNT</span>(<span class="pl-k">*</span>) <span class="pl-k">FROM</span> score <span class="pl-k">GROUP BY</span> c_no
<span class="pl-k">HAVING</span> <span class="pl-c1">COUNT</span>(c_no) <span class="pl-k">&gt;=</span> <span class="pl-c1">2</span> <span class="pl-k">AND</span> c_no <span class="pl-k">LIKE</span> <span class="pl-s"><span class="pl-pds">'</span>3%<span class="pl-pds">'</span></span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-------------+----------+</span>
| c_no  | <span class="pl-c1">AVG</span>(degree) | <span class="pl-c1">COUNT</span>(<span class="pl-k">*</span>) |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-------------+----------+</span>
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">85</span>.<span class="pl-c1">3333</span> |        <span class="pl-c1">3</span> |
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">76</span>.<span class="pl-c1">3333</span> |        <span class="pl-c1">3</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-------------+----------+</span></pre></div>
<h3><a id="user-content-多表查询---1" class="anchor" aria-hidden="true" href="#多表查询---1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>多表查询 - 1</h3>
<p><strong>查询所有学生的 <code>name</code>，以及该学生在 <code>score</code> 表中对应的 <code>c_no</code> 和 <code>degree</code> 。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> no, name <span class="pl-k">FROM</span> student;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+-----------+</span>
| no  | name      |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+-----------+</span>
| <span class="pl-c1">101</span> | 曾华      |
| <span class="pl-c1">102</span> | 匡明      |
| <span class="pl-c1">103</span> | 王丽      |
| <span class="pl-c1">104</span> | 李军      |
| <span class="pl-c1">105</span> | 王芳      |
| <span class="pl-c1">106</span> | 陆军      |
| <span class="pl-c1">107</span> | 王尼玛    |
| <span class="pl-c1">108</span> | 张全蛋    |
| <span class="pl-c1">109</span> | 赵铁柱    |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+-----------+</span>

<span class="pl-k">SELECT</span> s_no, c_no, degree <span class="pl-k">FROM</span> score;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">92</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">86</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">85</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">88</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">75</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">79</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">68</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">81</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span></pre></div>
<p>通过分析可以发现，只要把 <code>score</code> 表中的 <code>s_no</code> 字段值替换成 <code>student</code> 表中对应的 <code>name</code> 字段值就可以了，如何做呢？</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> FROM...: 表示从 student, score 表中查询</span>
<span class="pl-c"><span class="pl-c">--</span> WHERE 的条件表示为，只有在 student.no 和 score.s_no 相等时才显示出来。</span>
<span class="pl-k">SELECT</span> name, c_no, degree <span class="pl-k">FROM</span> student, score 
<span class="pl-k">WHERE</span> <span class="pl-c1">student</span>.<span class="pl-c1">no</span> <span class="pl-k">=</span> <span class="pl-c1">score</span>.<span class="pl-c1">s_no</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+-------+--------+</span>
| name      | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+-------+--------+</span>
| 王丽      | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">92</span> |
| 王丽      | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">86</span> |
| 王丽      | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">85</span> |
| 王芳      | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">88</span> |
| 王芳      | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">75</span> |
| 王芳      | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">79</span> |
| 赵铁柱    | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
| 赵铁柱    | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">68</span> |
| 赵铁柱    | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">81</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+-------+--------+</span></pre></div>
<h3><a id="user-content-多表查询---2" class="anchor" aria-hidden="true" href="#多表查询---2"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>多表查询 - 2</h3>
<p><strong>查询所有学生的 <code>no</code> 、课程名称 ( <code>course</code> 表中的 <code>name</code> ) 和成绩 ( <code>score</code> 表中的 <code>degree</code> ) 列。</strong></p>
<p>只有 <code>score</code> 关联学生的 <code>no</code> ，因此只要查询 <code>score</code> 表，就能找出所有和学生相关的 <code>no</code> 和 <code>degree</code> ：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> s_no, c_no, degree <span class="pl-k">FROM</span> score;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">92</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">86</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">85</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">88</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">75</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">79</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">68</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">81</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span></pre></div>
<p>然后查询 <code>course</code> 表：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-----------------+</span>
| no    | name            |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-----------------+</span>
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> | 计算机导论      |
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> | 操作系统        |
| <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> | 数字电路        |
| <span class="pl-c1">9</span><span class="pl-k">-</span><span class="pl-c1">888</span> | 高等数学        |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-----------------+</span></pre></div>
<p>只要把 <code>score</code> 表中的 <code>c_no</code> 替换成 <code>course</code> 表中对应的 <code>name</code> 字段值就可以了。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 增加一个查询字段 name，分别从 score、course 这两个表中查询。</span>
<span class="pl-c"><span class="pl-c">--</span> as 表示取一个该字段的别名。</span>
<span class="pl-k">SELECT</span> s_no, name <span class="pl-k">as</span> c_name, degree <span class="pl-k">FROM</span> score, course
<span class="pl-k">WHERE</span> <span class="pl-c1">score</span>.<span class="pl-c1">c_no</span> <span class="pl-k">=</span> <span class="pl-c1">course</span>.<span class="pl-c1">no</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-----------------+--------+</span>
| s_no | c_name          | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-----------------+--------+</span>
| <span class="pl-c1">103</span>  | 计算机导论      |     <span class="pl-c1">92</span> |
| <span class="pl-c1">105</span>  | 计算机导论      |     <span class="pl-c1">88</span> |
| <span class="pl-c1">109</span>  | 计算机导论      |     <span class="pl-c1">76</span> |
| <span class="pl-c1">103</span>  | 操作系统        |     <span class="pl-c1">86</span> |
| <span class="pl-c1">105</span>  | 操作系统        |     <span class="pl-c1">75</span> |
| <span class="pl-c1">109</span>  | 操作系统        |     <span class="pl-c1">68</span> |
| <span class="pl-c1">103</span>  | 数字电路        |     <span class="pl-c1">85</span> |
| <span class="pl-c1">105</span>  | 数字电路        |     <span class="pl-c1">79</span> |
| <span class="pl-c1">109</span>  | 数字电路        |     <span class="pl-c1">81</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-----------------+--------+</span></pre></div>
<h3><a id="user-content-三表关联查询" class="anchor" aria-hidden="true" href="#三表关联查询"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>三表关联查询</h3>
<p><strong>查询所有学生的 <code>name</code> 、课程名 ( <code>course</code> 表中的 <code>name</code> ) 和 <code>degree</code> 。</strong></p>
<p>只有 <code>score</code> 表中关联学生的学号和课堂号，我们只要围绕着 <code>score</code> 这张表查询就好了。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">92</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">86</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">85</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">88</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">75</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">79</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">68</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">81</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span></pre></div>
<p>只要把 <code>s_no</code> 和 <code>c_no</code> 替换成 <code>student</code> 和 <code>srouse</code> 表中对应的 <code>name</code> 字段值就好了。</p>
<p>首先把 <code>s_no</code> 替换成 <code>student</code> 表中的 <code>name</code> 字段：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> name, c_no, degree <span class="pl-k">FROM</span> student, score <span class="pl-k">WHERE</span> <span class="pl-c1">student</span>.<span class="pl-c1">no</span> <span class="pl-k">=</span> <span class="pl-c1">score</span>.<span class="pl-c1">s_no</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+-------+--------+</span>
| name      | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+-------+--------+</span>
| 王丽      | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">92</span> |
| 王丽      | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">86</span> |
| 王丽      | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">85</span> |
| 王芳      | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">88</span> |
| 王芳      | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">75</span> |
| 王芳      | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">79</span> |
| 赵铁柱    | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
| 赵铁柱    | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">68</span> |
| 赵铁柱    | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">81</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+-------+--------+</span></pre></div>
<p>再把 <code>c_no</code> 替换成 <code>course</code> 表中的 <code>name</code> 字段：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 课程表</span>
<span class="pl-k">SELECT</span> no, name <span class="pl-k">FROM</span> course;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-----------------+</span>
| no    | name            |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-----------------+</span>
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> | 计算机导论      |
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> | 操作系统        |
| <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> | 数字电路        |
| <span class="pl-c1">9</span><span class="pl-k">-</span><span class="pl-c1">888</span> | 高等数学        |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-----------------+</span>

<span class="pl-c"><span class="pl-c">--</span> 由于字段名存在重复，使用 "表名.字段名 as 别名" 代替。</span>
<span class="pl-k">SELECT</span> <span class="pl-c1">student</span>.<span class="pl-c1">name</span> <span class="pl-k">as</span> s_name, <span class="pl-c1">course</span>.<span class="pl-c1">name</span> <span class="pl-k">as</span> c_name, degree 
<span class="pl-k">FROM</span> student, score, course
<span class="pl-k">WHERE</span> <span class="pl-c1">student</span>.<span class="pl-c1">NO</span> <span class="pl-k">=</span> <span class="pl-c1">score</span>.<span class="pl-c1">s_no</span>
<span class="pl-k">AND</span> <span class="pl-c1">score</span>.<span class="pl-c1">c_no</span> <span class="pl-k">=</span> <span class="pl-c1">course</span>.<span class="pl-c1">no</span>;</pre></div>
<h3><a id="user-content-子查询加分组求平均分" class="anchor" aria-hidden="true" href="#子查询加分组求平均分"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>子查询加分组求平均分</h3>
<p><strong>查询 <code>95031</code> 班学生每门课程的平均成绩。</strong></p>
<p>在 <code>score</code> 表中根据 <code>student</code>  表的学生编号筛选出学生的课堂号和成绩：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> IN (..): 将筛选出的学生号当做 s_no 的条件查询</span>
<span class="pl-k">SELECT</span> s_no, c_no, degree <span class="pl-k">FROM</span> score
<span class="pl-k">WHERE</span> s_no <span class="pl-k">IN</span> (<span class="pl-k">SELECT</span> no <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> class <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>95031<span class="pl-pds">'</span></span>);
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">88</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">75</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">79</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">68</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">81</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span></pre></div>
<p>这时只要将 <code>c_no</code> 分组一下就能得出 <code>95031</code> 班学生每门课的平均成绩：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> c_no, <span class="pl-c1">AVG</span>(degree) <span class="pl-k">FROM</span> score
<span class="pl-k">WHERE</span> s_no <span class="pl-k">IN</span> (<span class="pl-k">SELECT</span> no <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> class <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>95031<span class="pl-pds">'</span></span>)
<span class="pl-k">GROUP BY</span> c_no;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-------------+</span>
| c_no  | <span class="pl-c1">AVG</span>(degree) |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-------------+</span>
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">82</span>.<span class="pl-c1">0000</span> |
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">71</span>.<span class="pl-c1">5000</span> |
| <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">80</span>.<span class="pl-c1">0000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-------------+</span></pre></div>
<h3><a id="user-content-子查询---1" class="anchor" aria-hidden="true" href="#子查询---1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>子查询 - 1</h3>
<p><strong>查询在 <code>3-105</code> 课程中，所有成绩高于 <code>109</code> 号同学的记录。</strong></p>
<p>首先筛选出课堂号为 <code>3-105</code> ，在找出所有成绩高于 <code>109</code> 号同学的的行。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score 
<span class="pl-k">WHERE</span> c_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span>
<span class="pl-k">AND</span> degree <span class="pl-k">&gt;</span> (<span class="pl-k">SELECT</span> degree <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> s_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>109<span class="pl-pds">'</span></span> <span class="pl-k">AND</span> c_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span>);</pre></div>
<h3><a id="user-content-子查询---2" class="anchor" aria-hidden="true" href="#子查询---2"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>子查询 - 2</h3>
<p><strong>查询所有成绩高于 <code>109</code> 号同学的 <code>3-105</code> 课程成绩记录。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 不限制课程号，只要成绩大于109号同学的3-105课程成绩就可以。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score
<span class="pl-k">WHERE</span> degree <span class="pl-k">&gt;</span> (<span class="pl-k">SELECT</span> degree <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> s_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>109<span class="pl-pds">'</span></span> <span class="pl-k">AND</span> c_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span>);</pre></div>
<h3><a id="user-content-year-函数与带-in-关键字查询" class="anchor" aria-hidden="true" href="#year-函数与带-in-关键字查询"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>YEAR 函数与带 IN 关键字查询</h3>
<p><strong>查询所有和 <code>101</code> 、<code>108</code> 号学生同年出生的 <code>no</code> 、<code>name</code> 、<code>birthday</code> 列。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> YEAR(..): 取出日期中的年份</span>
<span class="pl-k">SELECT</span> no, name, birthday <span class="pl-k">FROM</span> student
<span class="pl-k">WHERE</span> YEAR(birthday) <span class="pl-k">IN</span> (<span class="pl-k">SELECT</span> YEAR(birthday) <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> no <span class="pl-k">IN</span> (<span class="pl-c1">101</span>, <span class="pl-c1">108</span>));</pre></div>
<h3><a id="user-content-多层嵌套子查询" class="anchor" aria-hidden="true" href="#多层嵌套子查询"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>多层嵌套子查询</h3>
<p><strong>查询 <code>'张旭'</code> 教师任课的学生成绩表。</strong></p>
<p>首先找到教师编号：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> NO <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> NAME <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>张旭<span class="pl-pds">'</span></span></pre></div>
<p>通过 <code>sourse</code> 表找到该教师课程号：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> NO <span class="pl-k">FROM</span> course <span class="pl-k">WHERE</span> t_no <span class="pl-k">=</span> ( <span class="pl-k">SELECT</span> NO <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> NAME <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>张旭<span class="pl-pds">'</span></span> );</pre></div>
<p>通过筛选出的课程号查询成绩表：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> c_no <span class="pl-k">=</span> (
    <span class="pl-k">SELECT</span> no <span class="pl-k">FROM</span> course <span class="pl-k">WHERE</span> t_no <span class="pl-k">=</span> ( 
        <span class="pl-k">SELECT</span> no <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> NAME <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>张旭<span class="pl-pds">'</span></span> 
    )
);</pre></div>
<h3><a id="user-content-多表查询" class="anchor" aria-hidden="true" href="#多表查询"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>多表查询</h3>
<p><strong>查询某选修课程多于5个同学的教师姓名。</strong></p>
<p>首先在 <code>teacher</code> 表中，根据 <code>no</code> 字段来判断该教师的同一门课程是否有至少5名学员选修：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 查询 teacher 表</span>
<span class="pl-k">SELECT</span> no, name <span class="pl-k">FROM</span> teacher;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+--------+</span>
| no  | name   |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+--------+</span>
| <span class="pl-c1">804</span> | 李诚   |
| <span class="pl-c1">825</span> | 王萍   |
| <span class="pl-c1">831</span> | 刘冰   |
| <span class="pl-c1">856</span> | 张旭   |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+--------+</span>

<span class="pl-k">SELECT</span> name <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> no <span class="pl-k">IN</span> (
    <span class="pl-c"><span class="pl-c">--</span> 在这里找到对应的条件</span>
);</pre></div>
<p>查看和教师编号有有关的表的信息：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> course;
<span class="pl-c"><span class="pl-c">--</span> t_no: 教师编号</span>
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-----------------+------+</span>
| no    | name            | t_no |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-----------------+------+</span>
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> | 计算机导论      | <span class="pl-c1">825</span>  |
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> | 操作系统        | <span class="pl-c1">804</span>  |
| <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> | 数字电路        | <span class="pl-c1">856</span>  |
| <span class="pl-c1">9</span><span class="pl-k">-</span><span class="pl-c1">888</span> | 高等数学        | <span class="pl-c1">831</span>  |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-----------------+------+</span></pre></div>
<p>我们已经找到和教师编号有关的字段就在 <code>course</code> 表中，但是还无法知道哪门课程至少有5名学生选修，所以还需要根据 <code>score</code> 表来查询：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 在此之前向 score 插入一些数据，以便丰富查询条件。</span>
<span class="pl-k">INSERT INTO</span> score <span class="pl-k">VALUES</span> (<span class="pl-s"><span class="pl-pds">'</span>101<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>90<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> score <span class="pl-k">VALUES</span> (<span class="pl-s"><span class="pl-pds">'</span>102<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>91<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> score <span class="pl-k">VALUES</span> (<span class="pl-s"><span class="pl-pds">'</span>104<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>89<span class="pl-pds">'</span></span>);

<span class="pl-c"><span class="pl-c">--</span> 查询 score 表</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">101</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">90</span> |
| <span class="pl-c1">102</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">91</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">92</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">86</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">85</span> |
| <span class="pl-c1">104</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">89</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">88</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">75</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">79</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">68</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">81</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>

<span class="pl-c"><span class="pl-c">--</span> 在 score 表中将 c_no 作为分组，并且限制 c_no 持有至少 5 条数据。</span>
<span class="pl-k">SELECT</span> c_no <span class="pl-k">FROM</span> score <span class="pl-k">GROUP BY</span> c_no <span class="pl-k">HAVING</span> <span class="pl-c1">COUNT</span>(<span class="pl-k">*</span>) <span class="pl-k">&gt;</span> <span class="pl-c1">5</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+</span>
| c_no  |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+</span>
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+</span></pre></div>
<p>根据筛选出来的课程号，找出在某课程中，拥有至少5名学员的教师编号：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> t_no <span class="pl-k">FROM</span> course <span class="pl-k">WHERE</span> no <span class="pl-k">IN</span> (
    <span class="pl-k">SELECT</span> c_no <span class="pl-k">FROM</span> score <span class="pl-k">GROUP BY</span> c_no <span class="pl-k">HAVING</span> <span class="pl-c1">COUNT</span>(<span class="pl-k">*</span>) <span class="pl-k">&gt;</span> <span class="pl-c1">5</span>
);
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+</span>
| t_no |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+</span>
| <span class="pl-c1">825</span>  |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+</span></pre></div>
<p>在 <code>teacher</code> 表中，根据筛选出来的教师编号找到教师姓名：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> name <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> no <span class="pl-k">IN</span> (
    <span class="pl-c"><span class="pl-c">--</span> 最终条件</span>
    <span class="pl-k">SELECT</span> t_no <span class="pl-k">FROM</span> course <span class="pl-k">WHERE</span> no <span class="pl-k">IN</span> (
        <span class="pl-k">SELECT</span> c_no <span class="pl-k">FROM</span> score <span class="pl-k">GROUP BY</span> c_no <span class="pl-k">HAVING</span> <span class="pl-c1">COUNT</span>(<span class="pl-k">*</span>) <span class="pl-k">&gt;</span> <span class="pl-c1">5</span>
    )
);</pre></div>
<h3><a id="user-content-子查询---3" class="anchor" aria-hidden="true" href="#子查询---3"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>子查询 - 3</h3>
<p><strong>查询 “计算机系” 课程的成绩表。</strong></p>
<p>思路是，先找出 <code>course</code> 表中所有 <code>计算机系</code> 课程的编号，然后根据这个编号查询 <code>score</code> 表。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 通过 teacher 表查询所有 `计算机系` 的教师编号</span>
<span class="pl-k">SELECT</span> no, name, department <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> department <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>计算机系<span class="pl-pds">'</span></span>
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+--------+--------------+</span>
| no  | name   | department   |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+--------+--------------+</span>
| <span class="pl-c1">804</span> | 李诚   | 计算机系     |
| <span class="pl-c1">825</span> | 王萍   | 计算机系     |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+--------+--------------+</span>

<span class="pl-c"><span class="pl-c">--</span> 通过 course 表查询该教师的课程编号</span>
<span class="pl-k">SELECT</span> no <span class="pl-k">FROM</span> course <span class="pl-k">WHERE</span> t_no <span class="pl-k">IN</span> (
    <span class="pl-k">SELECT</span> no <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> department <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>计算机系<span class="pl-pds">'</span></span>
);
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+</span>
| no    |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+</span>
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+</span>

<span class="pl-c"><span class="pl-c">--</span> 根据筛选出来的课程号查询成绩表</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> c_no <span class="pl-k">IN</span> (
    <span class="pl-k">SELECT</span> no <span class="pl-k">FROM</span> course <span class="pl-k">WHERE</span> t_no <span class="pl-k">IN</span> (
        <span class="pl-k">SELECT</span> no <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> department <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>计算机系<span class="pl-pds">'</span></span>
    )
);
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">86</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">75</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">68</span> |
| <span class="pl-c1">101</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">90</span> |
| <span class="pl-c1">102</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">91</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">92</span> |
| <span class="pl-c1">104</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">89</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">88</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span></pre></div>
<h3><a id="user-content-union-和-notin-的使用" class="anchor" aria-hidden="true" href="#union-和-notin-的使用"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>UNION 和 NOTIN 的使用</h3>
<p><strong>查询 <code>计算机系</code> 与 <code>电子工程系</code> 中的不同职称的教师。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> NOT: 代表逻辑非</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> department <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>计算机系<span class="pl-pds">'</span></span> <span class="pl-k">AND</span> profession NOT <span class="pl-k">IN</span> (
    <span class="pl-k">SELECT</span> profession <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> department <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>电子工程系<span class="pl-pds">'</span></span>
)
<span class="pl-c"><span class="pl-c">--</span> 合并两个集</span>
<span class="pl-k">UNION</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> department <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>电子工程系<span class="pl-pds">'</span></span> <span class="pl-k">AND</span> profession NOT <span class="pl-k">IN</span> (
    <span class="pl-k">SELECT</span> profession <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> department <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>计算机系<span class="pl-pds">'</span></span>
);</pre></div>
<h3><a id="user-content-any-表示至少一个---desc--降序-" class="anchor" aria-hidden="true" href="#any-表示至少一个---desc--降序-"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>ANY 表示至少一个 - DESC ( 降序 )</h3>
<p><strong>查询课程 <code>3-105</code> 且成绩 至少 高于 <code>3-245</code> 的 <code>score</code> 表。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> c_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">101</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">90</span> |
| <span class="pl-c1">102</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">91</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">92</span> |
| <span class="pl-c1">104</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">89</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">88</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>

<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> c_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>3-245<span class="pl-pds">'</span></span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">86</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">75</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">68</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>

<span class="pl-c"><span class="pl-c">--</span> ANY: 符合SQL语句中的任意条件。</span>
<span class="pl-c"><span class="pl-c">--</span> 也就是说，在 3-105 成绩中，只要有一个大于从 3-245 筛选出来的任意行就符合条件，</span>
<span class="pl-c"><span class="pl-c">--</span> 最后根据降序查询结果。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> c_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span> <span class="pl-k">AND</span> degree <span class="pl-k">&gt;</span> ANY(
    <span class="pl-k">SELECT</span> degree <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> c_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>3-245<span class="pl-pds">'</span></span>
) <span class="pl-k">ORDER BY</span> degree <span class="pl-k">DESC</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">92</span> |
| <span class="pl-c1">102</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">91</span> |
| <span class="pl-c1">101</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">90</span> |
| <span class="pl-c1">104</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">89</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">88</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span></pre></div>
<h3><a id="user-content-表示所有的-all" class="anchor" aria-hidden="true" href="#表示所有的-all"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>表示所有的 ALL</h3>
<p><strong>查询课程 <code>3-105</code> 且成绩高于 <code>3-245</code> 的 <code>score</code> 表。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 只需对上一道题稍作修改。</span>
<span class="pl-c"><span class="pl-c">--</span> ALL: 符合SQL语句中的所有条件。</span>
<span class="pl-c"><span class="pl-c">--</span> 也就是说，在 3-105 每一行成绩中，都要大于从 3-245 筛选出来全部行才算符合条件。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> c_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>3-105<span class="pl-pds">'</span></span> <span class="pl-k">AND</span> degree <span class="pl-k">&gt;</span> ALL(
    <span class="pl-k">SELECT</span> degree <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> c_no <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>3-245<span class="pl-pds">'</span></span>
);
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">101</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">90</span> |
| <span class="pl-c1">102</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">91</span> |
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">92</span> |
| <span class="pl-c1">104</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">89</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">88</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span></pre></div>
<h3><a id="user-content-复制表的数据作为条件查询" class="anchor" aria-hidden="true" href="#复制表的数据作为条件查询"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>复制表的数据作为条件查询</h3>
<p><strong>查询某课程成绩比该课程平均成绩低的 <code>score</code> 表。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 查询平均分</span>
<span class="pl-k">SELECT</span> c_no, <span class="pl-c1">AVG</span>(degree) <span class="pl-k">FROM</span> score <span class="pl-k">GROUP BY</span> c_no;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-------------+</span>
| c_no  | <span class="pl-c1">AVG</span>(degree) |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-------------+</span>
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">87</span>.<span class="pl-c1">6667</span> |
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">76</span>.<span class="pl-c1">3333</span> |
| <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">81</span>.<span class="pl-c1">6667</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+-------------+</span>

<span class="pl-c"><span class="pl-c">--</span> 查询 score 表</span>
<span class="pl-k">SELECT</span> degree <span class="pl-k">FROM</span> score;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------+</span>
| degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------+</span>
|     <span class="pl-c1">90</span> |
|     <span class="pl-c1">91</span> |
|     <span class="pl-c1">92</span> |
|     <span class="pl-c1">86</span> |
|     <span class="pl-c1">85</span> |
|     <span class="pl-c1">89</span> |
|     <span class="pl-c1">88</span> |
|     <span class="pl-c1">75</span> |
|     <span class="pl-c1">79</span> |
|     <span class="pl-c1">76</span> |
|     <span class="pl-c1">68</span> |
|     <span class="pl-c1">81</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------+</span>

<span class="pl-c"><span class="pl-c">--</span> 将表 b 作用于表 a 中查询数据</span>
<span class="pl-c"><span class="pl-c">--</span> score a (b): 将表声明为 a (b)，</span>
<span class="pl-c"><span class="pl-c">--</span> 如此就能用 a.c_no = b.c_no 作为条件执行查询了。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score a <span class="pl-k">WHERE</span> degree <span class="pl-k">&lt;</span> (
    (<span class="pl-k">SELECT</span> <span class="pl-c1">AVG</span>(degree) <span class="pl-k">FROM</span> score b <span class="pl-k">WHERE</span> <span class="pl-c1">a</span>.<span class="pl-c1">c_no</span> <span class="pl-k">=</span> <span class="pl-c1">b</span>.<span class="pl-c1">c_no</span>)
);
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">75</span> |
| <span class="pl-c1">105</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">79</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> |     <span class="pl-c1">68</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> |     <span class="pl-c1">81</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span></pre></div>
<h3><a id="user-content-子查询---4" class="anchor" aria-hidden="true" href="#子查询---4"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>子查询 - 4</h3>
<p><strong>查询所有任课 ( 在 <code>course</code> 表里有课程 ) 教师的 <code>name</code> 和 <code>department</code></strong> 。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> name, department <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> no <span class="pl-k">IN</span> (<span class="pl-k">SELECT</span> t_no <span class="pl-k">FROM</span> course);
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------+-----------------+</span>
| name   | department      |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------+-----------------+</span>
| 李诚   | 计算机系        |
| 王萍   | 计算机系        |
| 刘冰   | 电子工程系      |
| 张旭   | 电子工程系      |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------+-----------------+</span></pre></div>
<h3><a id="user-content-条件加组筛选" class="anchor" aria-hidden="true" href="#条件加组筛选"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>条件加组筛选</h3>
<p><strong>查询 <code>student</code> 表中至少有 2 名男生的 <code>class</code> 。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 查看学生表信息</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> student;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+-----------+-----+------------+-------+</span>
| no  | name      | sex | birthday   | class |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+-----------+-----+------------+-------+</span>
| <span class="pl-c1">101</span> | 曾华      | 男  | <span class="pl-c1">1977</span><span class="pl-k">-</span><span class="pl-c1">09</span><span class="pl-k">-</span><span class="pl-c1">01</span> | <span class="pl-c1">95033</span> |
| <span class="pl-c1">102</span> | 匡明      | 男  | <span class="pl-c1">1975</span><span class="pl-k">-</span><span class="pl-c1">10</span><span class="pl-k">-</span><span class="pl-c1">02</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">103</span> | 王丽      | 女  | <span class="pl-c1">1976</span><span class="pl-k">-</span><span class="pl-c1">01</span><span class="pl-k">-</span><span class="pl-c1">23</span> | <span class="pl-c1">95033</span> |
| <span class="pl-c1">104</span> | 李军      | 男  | <span class="pl-c1">1976</span><span class="pl-k">-</span><span class="pl-c1">02</span><span class="pl-k">-</span><span class="pl-c1">20</span> | <span class="pl-c1">95033</span> |
| <span class="pl-c1">105</span> | 王芳      | 女  | <span class="pl-c1">1975</span><span class="pl-k">-</span><span class="pl-c1">02</span><span class="pl-k">-</span><span class="pl-c1">10</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">106</span> | 陆军      | 男  | <span class="pl-c1">1974</span><span class="pl-k">-</span><span class="pl-c1">06</span><span class="pl-k">-</span><span class="pl-c1">03</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">107</span> | 王尼玛    | 男  | <span class="pl-c1">1976</span><span class="pl-k">-</span><span class="pl-c1">02</span><span class="pl-k">-</span><span class="pl-c1">20</span> | <span class="pl-c1">95033</span> |
| <span class="pl-c1">108</span> | 张全蛋    | 男  | <span class="pl-c1">1975</span><span class="pl-k">-</span><span class="pl-c1">02</span><span class="pl-k">-</span><span class="pl-c1">10</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">109</span> | 赵铁柱    | 男  | <span class="pl-c1">1974</span><span class="pl-k">-</span><span class="pl-c1">06</span><span class="pl-k">-</span><span class="pl-c1">03</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">110</span> | 张飞      | 男  | <span class="pl-c1">1974</span><span class="pl-k">-</span><span class="pl-c1">06</span><span class="pl-k">-</span><span class="pl-c1">03</span> | <span class="pl-c1">95038</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+-----------+-----+------------+-------+</span>

<span class="pl-c"><span class="pl-c">--</span> 只查询性别为男，然后按 class 分组，并限制 class 行大于 1。</span>
<span class="pl-k">SELECT</span> class <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> sex <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>男<span class="pl-pds">'</span></span> <span class="pl-k">GROUP BY</span> class <span class="pl-k">HAVING</span> <span class="pl-c1">COUNT</span>(<span class="pl-k">*</span>) <span class="pl-k">&gt;</span> <span class="pl-c1">1</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+</span>
| class |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+</span>
| <span class="pl-c1">95033</span> |
| <span class="pl-c1">95031</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+</span></pre></div>
<h3><a id="user-content-notlike-模糊查询取反" class="anchor" aria-hidden="true" href="#notlike-模糊查询取反"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>NOTLIKE 模糊查询取反</h3>
<p><strong>查询 <code>student</code> 表中不姓 "王" 的同学记录。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> NOT: 取反</span>
<span class="pl-c"><span class="pl-c">--</span> LIKE: 模糊查询</span>
mysql<span class="pl-k">&gt;</span> <span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> name NOT <span class="pl-k">LIKE</span> <span class="pl-s"><span class="pl-pds">'</span>王%<span class="pl-pds">'</span></span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+-----------+-----+------------+-------+</span>
| no  | name      | sex | birthday   | class |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+-----------+-----+------------+-------+</span>
| <span class="pl-c1">101</span> | 曾华      | 男  | <span class="pl-c1">1977</span><span class="pl-k">-</span><span class="pl-c1">09</span><span class="pl-k">-</span><span class="pl-c1">01</span> | <span class="pl-c1">95033</span> |
| <span class="pl-c1">102</span> | 匡明      | 男  | <span class="pl-c1">1975</span><span class="pl-k">-</span><span class="pl-c1">10</span><span class="pl-k">-</span><span class="pl-c1">02</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">104</span> | 李军      | 男  | <span class="pl-c1">1976</span><span class="pl-k">-</span><span class="pl-c1">02</span><span class="pl-k">-</span><span class="pl-c1">20</span> | <span class="pl-c1">95033</span> |
| <span class="pl-c1">106</span> | 陆军      | 男  | <span class="pl-c1">1974</span><span class="pl-k">-</span><span class="pl-c1">06</span><span class="pl-k">-</span><span class="pl-c1">03</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">108</span> | 张全蛋    | 男  | <span class="pl-c1">1975</span><span class="pl-k">-</span><span class="pl-c1">02</span><span class="pl-k">-</span><span class="pl-c1">10</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">109</span> | 赵铁柱    | 男  | <span class="pl-c1">1974</span><span class="pl-k">-</span><span class="pl-c1">06</span><span class="pl-k">-</span><span class="pl-c1">03</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">110</span> | 张飞      | 男  | <span class="pl-c1">1974</span><span class="pl-k">-</span><span class="pl-c1">06</span><span class="pl-k">-</span><span class="pl-c1">03</span> | <span class="pl-c1">95038</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+-----------+-----+------------+-------+</span></pre></div>
<h3><a id="user-content-year-与-now-函数" class="anchor" aria-hidden="true" href="#year-与-now-函数"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>YEAR 与 NOW 函数</h3>
<p><strong>查询 <code>student</code> 表中每个学生的姓名和年龄。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 使用函数 YEAR(NOW()) 计算出当前年份，减去出生年份后得出年龄。</span>
<span class="pl-k">SELECT</span> name, YEAR(NOW()) <span class="pl-k">-</span> YEAR(birthday) <span class="pl-k">as</span> age <span class="pl-k">FROM</span> student;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+------+</span>
| name      | age  |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+------+</span>
| 曾华      |   <span class="pl-c1">42</span> |
| 匡明      |   <span class="pl-c1">44</span> |
| 王丽      |   <span class="pl-c1">43</span> |
| 李军      |   <span class="pl-c1">43</span> |
| 王芳      |   <span class="pl-c1">44</span> |
| 陆军      |   <span class="pl-c1">45</span> |
| 王尼玛    |   <span class="pl-c1">43</span> |
| 张全蛋    |   <span class="pl-c1">44</span> |
| 赵铁柱    |   <span class="pl-c1">45</span> |
| 张飞      |   <span class="pl-c1">45</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+------+</span></pre></div>
<h3><a id="user-content-max-与-min-函数" class="anchor" aria-hidden="true" href="#max-与-min-函数"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>MAX 与 MIN 函数</h3>
<p><strong>查询 <code>student</code> 表中最大和最小的 <code>birthday</code> 值。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> <span class="pl-c1">MAX</span>(birthday), <span class="pl-c1">MIN</span>(birthday) <span class="pl-k">FROM</span> student;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-------------+---------------+</span>
| <span class="pl-c1">MAX</span>(birthday) | <span class="pl-c1">MIN</span>(birthday) |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-------------+---------------+</span>
| <span class="pl-c1">1977</span><span class="pl-k">-</span><span class="pl-c1">09</span><span class="pl-k">-</span><span class="pl-c1">01</span>    | <span class="pl-c1">1974</span><span class="pl-k">-</span><span class="pl-c1">06</span><span class="pl-k">-</span><span class="pl-c1">03</span>    |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-------------+---------------+</span></pre></div>
<h3><a id="user-content-多段排序" class="anchor" aria-hidden="true" href="#多段排序"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>多段排序</h3>
<p><strong>以 <code>class</code> 和 <code>birthday</code> 从大到小的顺序查询 <code>student</code> 表。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> student <span class="pl-k">ORDER BY</span> class <span class="pl-k">DESC</span>, birthday;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+-----------+-----+------------+-------+</span>
| no  | name      | sex | birthday   | class |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+-----------+-----+------------+-------+</span>
| <span class="pl-c1">110</span> | 张飞      | 男  | <span class="pl-c1">1974</span><span class="pl-k">-</span><span class="pl-c1">06</span><span class="pl-k">-</span><span class="pl-c1">03</span> | <span class="pl-c1">95038</span> |
| <span class="pl-c1">103</span> | 王丽      | 女  | <span class="pl-c1">1976</span><span class="pl-k">-</span><span class="pl-c1">01</span><span class="pl-k">-</span><span class="pl-c1">23</span> | <span class="pl-c1">95033</span> |
| <span class="pl-c1">104</span> | 李军      | 男  | <span class="pl-c1">1976</span><span class="pl-k">-</span><span class="pl-c1">02</span><span class="pl-k">-</span><span class="pl-c1">20</span> | <span class="pl-c1">95033</span> |
| <span class="pl-c1">107</span> | 王尼玛    | 男  | <span class="pl-c1">1976</span><span class="pl-k">-</span><span class="pl-c1">02</span><span class="pl-k">-</span><span class="pl-c1">20</span> | <span class="pl-c1">95033</span> |
| <span class="pl-c1">101</span> | 曾华      | 男  | <span class="pl-c1">1977</span><span class="pl-k">-</span><span class="pl-c1">09</span><span class="pl-k">-</span><span class="pl-c1">01</span> | <span class="pl-c1">95033</span> |
| <span class="pl-c1">106</span> | 陆军      | 男  | <span class="pl-c1">1974</span><span class="pl-k">-</span><span class="pl-c1">06</span><span class="pl-k">-</span><span class="pl-c1">03</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">109</span> | 赵铁柱    | 男  | <span class="pl-c1">1974</span><span class="pl-k">-</span><span class="pl-c1">06</span><span class="pl-k">-</span><span class="pl-c1">03</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">105</span> | 王芳      | 女  | <span class="pl-c1">1975</span><span class="pl-k">-</span><span class="pl-c1">02</span><span class="pl-k">-</span><span class="pl-c1">10</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">108</span> | 张全蛋    | 男  | <span class="pl-c1">1975</span><span class="pl-k">-</span><span class="pl-c1">02</span><span class="pl-k">-</span><span class="pl-c1">10</span> | <span class="pl-c1">95031</span> |
| <span class="pl-c1">102</span> | 匡明      | 男  | <span class="pl-c1">1975</span><span class="pl-k">-</span><span class="pl-c1">10</span><span class="pl-k">-</span><span class="pl-c1">02</span> | <span class="pl-c1">95031</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+-----------+-----+------------+-------+</span></pre></div>
<h3><a id="user-content-子查询---5" class="anchor" aria-hidden="true" href="#子查询---5"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>子查询 - 5</h3>
<p><strong>查询 "男" 教师及其所上的课程。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> course <span class="pl-k">WHERE</span> t_no <span class="pl-k">in</span> (<span class="pl-k">SELECT</span> no <span class="pl-k">FROM</span> teacher <span class="pl-k">WHERE</span> sex <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>男<span class="pl-pds">'</span></span>);
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+--------------+------+</span>
| no    | name         | t_no |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+--------------+------+</span>
| <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> | 操作系统     | <span class="pl-c1">804</span>  |
| <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> | 数字电路     | <span class="pl-c1">856</span>  |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>-----+--------------+------+</span></pre></div>
<h3><a id="user-content-max-函数与子查询" class="anchor" aria-hidden="true" href="#max-函数与子查询"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>MAX 函数与子查询</h3>
<p><strong>查询最高分同学的 <code>score</code> 表。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 找出最高成绩（该查询只能有一个结果）</span>
<span class="pl-k">SELECT</span> <span class="pl-c1">MAX</span>(degree) <span class="pl-k">FROM</span> score;

<span class="pl-c"><span class="pl-c">--</span> 根据上面的条件筛选出所有最高成绩表，</span>
<span class="pl-c"><span class="pl-c">--</span> 该查询可能有多个结果，假设 degree 值多次符合条件。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> degree <span class="pl-k">=</span> (<span class="pl-k">SELECT</span> <span class="pl-c1">MAX</span>(degree) <span class="pl-k">FROM</span> score);
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">92</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span></pre></div>
<h3><a id="user-content-子查询---6" class="anchor" aria-hidden="true" href="#子查询---6"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>子查询 - 6</h3>
<p><strong>查询和 "李军" 同性别的所有同学 <code>name</code> 。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 首先将李军的性别作为条件取出来</span>
<span class="pl-k">SELECT</span> sex <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>李军<span class="pl-pds">'</span></span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+</span>
| sex |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+</span>
| 男  |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---+</span>

<span class="pl-c"><span class="pl-c">--</span> 根据性别查询 name 和 sex</span>
<span class="pl-k">SELECT</span> name, sex <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> sex <span class="pl-k">=</span> (
    <span class="pl-k">SELECT</span> sex <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>李军<span class="pl-pds">'</span></span>
);
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+-----+</span>
| name      | sex |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+-----+</span>
| 曾华      | 男  |
| 匡明      | 男  |
| 李军      | 男  |
| 陆军      | 男  |
| 王尼玛    | 男  |
| 张全蛋    | 男  |
| 赵铁柱    | 男  |
| 张飞      | 男  |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+-----+</span></pre></div>
<h3><a id="user-content-子查询---7" class="anchor" aria-hidden="true" href="#子查询---7"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>子查询 - 7</h3>
<p><strong>查询和 "李军" 同性别且同班的同学 <code>name</code> 。</strong></p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> name, sex, class <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> sex <span class="pl-k">=</span> (
    <span class="pl-k">SELECT</span> sex <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>李军<span class="pl-pds">'</span></span>
) <span class="pl-k">AND</span> class <span class="pl-k">=</span> (
    <span class="pl-k">SELECT</span> class <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>李军<span class="pl-pds">'</span></span>
);
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+-----+-------+</span>
| name      | sex | class |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+-----+-------+</span>
| 曾华      | 男  | <span class="pl-c1">95033</span> |
| 李军      | 男  | <span class="pl-c1">95033</span> |
| 王尼玛    | 男  | <span class="pl-c1">95033</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>---------+-----+-------+</span></pre></div>
<h3><a id="user-content-子查询---8" class="anchor" aria-hidden="true" href="#子查询---8"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>子查询 - 8</h3>
<p><strong>查询所有选修 "计算机导论" 课程的 "男" 同学成绩表。</strong></p>
<p>需要的 "计算机导论" 和性别为 "男" 的编号可以在 <code>course</code> 和 <code>student</code> 表中找到。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> score <span class="pl-k">WHERE</span> c_no <span class="pl-k">=</span> (
    <span class="pl-k">SELECT</span> no <span class="pl-k">FROM</span> course <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>计算机导论<span class="pl-pds">'</span></span>
) <span class="pl-k">AND</span> s_no <span class="pl-k">IN</span> (
    <span class="pl-k">SELECT</span> no <span class="pl-k">FROM</span> student <span class="pl-k">WHERE</span> sex <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>男<span class="pl-pds">'</span></span>
);
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| s_no | c_no  | degree |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span>
| <span class="pl-c1">101</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">90</span> |
| <span class="pl-c1">102</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">91</span> |
| <span class="pl-c1">104</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">89</span> |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> |     <span class="pl-c1">76</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+--------+</span></pre></div>
<h3><a id="user-content-按等级查询" class="anchor" aria-hidden="true" href="#按等级查询"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>按等级查询</h3>
<p>建立一个 <code>grade</code> 表代表学生的成绩等级，并插入数据：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">grade</span> (
    low <span class="pl-k">INT</span>(<span class="pl-c1">3</span>),
    upp <span class="pl-k">INT</span>(<span class="pl-c1">3</span>),
    grade <span class="pl-k">char</span>(<span class="pl-c1">1</span>)
);

<span class="pl-k">INSERT INTO</span> grade <span class="pl-k">VALUES</span> (<span class="pl-c1">90</span>, <span class="pl-c1">100</span>, <span class="pl-s"><span class="pl-pds">'</span>A<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> grade <span class="pl-k">VALUES</span> (<span class="pl-c1">80</span>, <span class="pl-c1">89</span>, <span class="pl-s"><span class="pl-pds">'</span>B<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> grade <span class="pl-k">VALUES</span> (<span class="pl-c1">70</span>, <span class="pl-c1">79</span>, <span class="pl-s"><span class="pl-pds">'</span>C<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> grade <span class="pl-k">VALUES</span> (<span class="pl-c1">60</span>, <span class="pl-c1">69</span>, <span class="pl-s"><span class="pl-pds">'</span>D<span class="pl-pds">'</span></span>);
<span class="pl-k">INSERT INTO</span> grade <span class="pl-k">VALUES</span> (<span class="pl-c1">0</span>, <span class="pl-c1">59</span>, <span class="pl-s"><span class="pl-pds">'</span>E<span class="pl-pds">'</span></span>);

<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> grade;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+------+-------+</span>
| low  | upp  | grade |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+------+-------+</span>
|   <span class="pl-c1">90</span> |  <span class="pl-c1">100</span> | A     |
|   <span class="pl-c1">80</span> |   <span class="pl-c1">89</span> | B     |
|   <span class="pl-c1">70</span> |   <span class="pl-c1">79</span> | C     |
|   <span class="pl-c1">60</span> |   <span class="pl-c1">69</span> | D     |
|    <span class="pl-c1">0</span> |   <span class="pl-c1">59</span> | E     |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+------+-------+</span></pre></div>
<p><strong>查询所有学生的 <code>s_no</code> 、<code>c_no</code> 和 <code>grade</code> 列。</strong></p>
<p>思路是，使用区间 ( <code>BETWEEN</code> ) 查询，判断学生的成绩 ( <code>degree</code> )  在 <code>grade</code> 表的 <code>low</code> 和 <code>upp</code> 之间。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> s_no, c_no, grade <span class="pl-k">FROM</span> score, grade 
<span class="pl-k">WHERE</span> degree BETWEEN low <span class="pl-k">AND</span> upp;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+-------+</span>
| s_no | c_no  | grade |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+-------+</span>
| <span class="pl-c1">101</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> | A     |
| <span class="pl-c1">102</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> | A     |
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> | A     |
| <span class="pl-c1">103</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> | B     |
| <span class="pl-c1">103</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> | B     |
| <span class="pl-c1">104</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> | B     |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> | B     |
| <span class="pl-c1">105</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> | C     |
| <span class="pl-c1">105</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> | C     |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">105</span> | C     |
| <span class="pl-c1">109</span>  | <span class="pl-c1">3</span><span class="pl-k">-</span><span class="pl-c1">245</span> | D     |
| <span class="pl-c1">109</span>  | <span class="pl-c1">6</span><span class="pl-k">-</span><span class="pl-c1">166</span> | B     |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-------+-------+</span></pre></div>
<h3><a id="user-content-连接查询" class="anchor" aria-hidden="true" href="#连接查询"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>连接查询</h3>
<p>准备用于测试连接查询的数据：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">CREATE</span> <span class="pl-k">DATABASE</span> <span class="pl-en">testJoin</span>;

<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">person</span> (
    id <span class="pl-k">INT</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    cardId <span class="pl-k">INT</span>
);

<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">card</span> (
    id <span class="pl-k">INT</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>)
);

<span class="pl-k">INSERT INTO</span> card <span class="pl-k">VALUES</span> (<span class="pl-c1">1</span>, <span class="pl-s"><span class="pl-pds">'</span>饭卡<span class="pl-pds">'</span></span>), (<span class="pl-c1">2</span>, <span class="pl-s"><span class="pl-pds">'</span>建行卡<span class="pl-pds">'</span></span>), (<span class="pl-c1">3</span>, <span class="pl-s"><span class="pl-pds">'</span>农行卡<span class="pl-pds">'</span></span>), (<span class="pl-c1">4</span>, <span class="pl-s"><span class="pl-pds">'</span>工商卡<span class="pl-pds">'</span></span>), (<span class="pl-c1">5</span>, <span class="pl-s"><span class="pl-pds">'</span>邮政卡<span class="pl-pds">'</span></span>);
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> card;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-----------+</span>
| id   | name      |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-----------+</span>
|    <span class="pl-c1">1</span> | 饭卡      |
|    <span class="pl-c1">2</span> | 建行卡    |
|    <span class="pl-c1">3</span> | 农行卡    |
|    <span class="pl-c1">4</span> | 工商卡    |
|    <span class="pl-c1">5</span> | 邮政卡    |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+-----------+</span>

<span class="pl-k">INSERT INTO</span> person <span class="pl-k">VALUES</span> (<span class="pl-c1">1</span>, <span class="pl-s"><span class="pl-pds">'</span>张三<span class="pl-pds">'</span></span>, <span class="pl-c1">1</span>), (<span class="pl-c1">2</span>, <span class="pl-s"><span class="pl-pds">'</span>李四<span class="pl-pds">'</span></span>, <span class="pl-c1">3</span>), (<span class="pl-c1">3</span>, <span class="pl-s"><span class="pl-pds">'</span>王五<span class="pl-pds">'</span></span>, <span class="pl-c1">6</span>);
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> person;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+</span>
| id   | name   | cardId |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+</span>
|    <span class="pl-c1">1</span> | 张三   |      <span class="pl-c1">1</span> |
|    <span class="pl-c1">2</span> | 李四   |      <span class="pl-c1">3</span> |
|    <span class="pl-c1">3</span> | 王五   |      <span class="pl-c1">6</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+</span></pre></div>
<p>分析两张表发现，<code>person</code> 表并没有为 <code>cardId</code> 字段设置一个在 <code>card</code> 表中对应的 <code>id</code> 外键。如果设置了的话，<code>person</code> 中 <code>cardId</code> 字段值为 <code>6</code> 的行就插不进去，因为该 <code>cardId</code> 值在 <code>card</code> 表中并没有。</p>
<h4><a id="user-content-内连接" class="anchor" aria-hidden="true" href="#内连接"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>内连接</h4>
<p>要查询这两张表中有关系的数据，可以使用 <code>INNER JOIN</code> ( 内连接 ) 将它们连接在一起。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> INNER JOIN: 表示为内连接，将两张表拼接在一起。</span>
<span class="pl-c"><span class="pl-c">--</span> on: 表示要执行某个条件。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> person <span class="pl-k">INNER JOIN</span> card <span class="pl-k">on</span> <span class="pl-c1">person</span>.<span class="pl-c1">cardId</span> <span class="pl-k">=</span> <span class="pl-c1">card</span>.<span class="pl-c1">id</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+------+-----------+</span>
| id   | name   | cardId | id   | name      |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+------+-----------+</span>
|    <span class="pl-c1">1</span> | 张三   |      <span class="pl-c1">1</span> |    <span class="pl-c1">1</span> | 饭卡      |
|    <span class="pl-c1">2</span> | 李四   |      <span class="pl-c1">3</span> |    <span class="pl-c1">3</span> | 农行卡    |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+------+-----------+</span>

<span class="pl-c"><span class="pl-c">--</span> 将 INNER 关键字省略掉，结果也是一样的。</span>
<span class="pl-c"><span class="pl-c">--</span> SELECT * FROM person JOIN card on person.cardId = card.id;</span></pre></div>
<blockquote>
<p>注意：<code>card</code> 的整张表被连接到了右边。</p>
</blockquote>
<h4><a id="user-content-左外连接" class="anchor" aria-hidden="true" href="#左外连接"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>左外连接</h4>
<p>完整显示左边的表 ( <code>person</code> ) ，右边的表如果符合条件就显示，不符合则补 <code>NULL</code> 。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> LEFT JOIN 也叫做 LEFT OUTER JOIN，用这两种方式的查询结果是一样的。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> person <span class="pl-k">LEFT JOIN</span> card <span class="pl-k">on</span> <span class="pl-c1">person</span>.<span class="pl-c1">cardId</span> <span class="pl-k">=</span> <span class="pl-c1">card</span>.<span class="pl-c1">id</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+------+-----------+</span>
| id   | name   | cardId | id   | name      |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+------+-----------+</span>
|    <span class="pl-c1">1</span> | 张三   |      <span class="pl-c1">1</span> |    <span class="pl-c1">1</span> | 饭卡      |
|    <span class="pl-c1">2</span> | 李四   |      <span class="pl-c1">3</span> |    <span class="pl-c1">3</span> | 农行卡    |
|    <span class="pl-c1">3</span> | 王五   |      <span class="pl-c1">6</span> | <span class="pl-k">NULL</span> | <span class="pl-k">NULL</span>      |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+------+-----------+</span></pre></div>
<h4><a id="user-content-右外链接" class="anchor" aria-hidden="true" href="#右外链接"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>右外链接</h4>
<p>完整显示右边的表 ( <code>card</code> ) ，左边的表如果符合条件就显示，不符合则补 <code>NULL</code> 。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> person <span class="pl-k">RIGHT JOIN</span> card <span class="pl-k">on</span> <span class="pl-c1">person</span>.<span class="pl-c1">cardId</span> <span class="pl-k">=</span> <span class="pl-c1">card</span>.<span class="pl-c1">id</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+------+-----------+</span>
| id   | name   | cardId | id   | name      |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+------+-----------+</span>
|    <span class="pl-c1">1</span> | 张三   |      <span class="pl-c1">1</span> |    <span class="pl-c1">1</span> | 饭卡      |
|    <span class="pl-c1">2</span> | 李四   |      <span class="pl-c1">3</span> |    <span class="pl-c1">3</span> | 农行卡    |
| <span class="pl-k">NULL</span> | <span class="pl-k">NULL</span>   |   <span class="pl-k">NULL</span> |    <span class="pl-c1">2</span> | 建行卡    |
| <span class="pl-k">NULL</span> | <span class="pl-k">NULL</span>   |   <span class="pl-k">NULL</span> |    <span class="pl-c1">4</span> | 工商卡    |
| <span class="pl-k">NULL</span> | <span class="pl-k">NULL</span>   |   <span class="pl-k">NULL</span> |    <span class="pl-c1">5</span> | 邮政卡    |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+------+-----------+</span></pre></div>
<h4><a id="user-content-全外链接" class="anchor" aria-hidden="true" href="#全外链接"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>全外链接</h4>
<p>完整显示两张表的全部数据。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> MySQL 不支持这种语法的全外连接</span>
<span class="pl-c"><span class="pl-c">--</span> SELECT * FROM person FULL JOIN card on person.cardId = card.id;</span>
<span class="pl-c"><span class="pl-c">--</span> 出现错误：</span>
<span class="pl-c"><span class="pl-c">--</span> ERROR 1054 (42S22): Unknown column 'person.cardId' in 'on clause'</span>

<span class="pl-c"><span class="pl-c">--</span> MySQL全连接语法，使用 UNION 将两张表合并在一起。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> person <span class="pl-k">LEFT JOIN</span> card <span class="pl-k">on</span> <span class="pl-c1">person</span>.<span class="pl-c1">cardId</span> <span class="pl-k">=</span> <span class="pl-c1">card</span>.<span class="pl-c1">id</span>
<span class="pl-k">UNION</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> person <span class="pl-k">RIGHT JOIN</span> card <span class="pl-k">on</span> <span class="pl-c1">person</span>.<span class="pl-c1">cardId</span> <span class="pl-k">=</span> <span class="pl-c1">card</span>.<span class="pl-c1">id</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+------+-----------+</span>
| id   | name   | cardId | id   | name      |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+------+-----------+</span>
|    <span class="pl-c1">1</span> | 张三   |      <span class="pl-c1">1</span> |    <span class="pl-c1">1</span> | 饭卡      |
|    <span class="pl-c1">2</span> | 李四   |      <span class="pl-c1">3</span> |    <span class="pl-c1">3</span> | 农行卡    |
|    <span class="pl-c1">3</span> | 王五   |      <span class="pl-c1">6</span> | <span class="pl-k">NULL</span> | <span class="pl-k">NULL</span>      |
| <span class="pl-k">NULL</span> | <span class="pl-k">NULL</span>   |   <span class="pl-k">NULL</span> |    <span class="pl-c1">2</span> | 建行卡    |
| <span class="pl-k">NULL</span> | <span class="pl-k">NULL</span>   |   <span class="pl-k">NULL</span> |    <span class="pl-c1">4</span> | 工商卡    |
| <span class="pl-k">NULL</span> | <span class="pl-k">NULL</span>   |   <span class="pl-k">NULL</span> |    <span class="pl-c1">5</span> | 邮政卡    |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----+--------+--------+------+-----------+</span></pre></div>
<h2><a id="user-content-事务" class="anchor" aria-hidden="true" href="#事务"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>事务</h2>
<p>在 MySQL 中，事务其实是一个最小的不可分割的工作单元。事务能够<strong>保证一个业务的完整性</strong>。</p>
<p>比如我们的银行转账：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> a -&gt; -100</span>
<span class="pl-k">UPDATE</span> user <span class="pl-k">set</span> <span class="pl-k">money</span> <span class="pl-k">=</span> <span class="pl-k">money</span> <span class="pl-k">-</span> <span class="pl-c1">100</span> <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>a<span class="pl-pds">'</span></span>;

<span class="pl-c"><span class="pl-c">--</span> b -&gt; +100</span>
<span class="pl-k">UPDATE</span> user <span class="pl-k">set</span> <span class="pl-k">money</span> <span class="pl-k">=</span> <span class="pl-k">money</span> <span class="pl-k">+</span> <span class="pl-c1">100</span> <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>b<span class="pl-pds">'</span></span>;</pre></div>
<p>在实际项目中，假设只有一条 SQL 语句执行成功，而另外一条执行失败了，就会出现数据前后不一致。</p>
<p>因此，在执行多条有关联 SQL 语句时，<strong>事务</strong>可能会要求这些 SQL 语句要么同时执行成功，要么就都执行失败。</p>
<h3><a id="user-content-如何控制事务---commit--rollback" class="anchor" aria-hidden="true" href="#如何控制事务---commit--rollback"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>如何控制事务 - COMMIT / ROLLBACK</h3>
<p>在 MySQL 中，事务的<strong>自动提交</strong>状态默认是开启的。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 查询事务的自动提交状态</span>
<span class="pl-k">SELECT</span> @@AUTOCOMMIT;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------+</span>
| @@AUTOCOMMIT |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------+</span>
|            <span class="pl-c1">1</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------+</span></pre></div>
<p><strong>自动提交的作用</strong>：当我们执行一条 SQL 语句的时候，其产生的效果就会立即体现出来，且不能<strong>回滚</strong>。</p>
<p>什么是回滚？举个例子：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">CREATE</span> <span class="pl-k">DATABASE</span> <span class="pl-en">bank</span>;

USE bank;

<span class="pl-k">CREATE</span> <span class="pl-k">TABLE</span> <span class="pl-en">user</span> (
    id <span class="pl-k">INT</span> <span class="pl-k">PRIMARY KEY</span>,
    name <span class="pl-k">VARCHAR</span>(<span class="pl-c1">20</span>),
    <span class="pl-k">money</span> <span class="pl-k">INT</span>
);

<span class="pl-k">INSERT INTO</span> user <span class="pl-k">VALUES</span> (<span class="pl-c1">1</span>, <span class="pl-s"><span class="pl-pds">'</span>a<span class="pl-pds">'</span></span>, <span class="pl-c1">1000</span>);

<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
| id | name | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
|  <span class="pl-c1">1</span> | a    |  <span class="pl-c1">1000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span></pre></div>
<p>可以看到，在执行插入语句后数据立刻生效，原因是 MySQL 中的事务自动将它<strong>提交</strong>到了数据库中。那么所谓<strong>回滚</strong>的意思就是，撤销执行过的所有 SQL 语句，使其回滚到<strong>最后一次提交</strong>数据时的状态。</p>
<p>在 MySQL 中使用 <code>ROLLBACK</code> 执行回滚：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 回滚到最后一次提交</span>
<span class="pl-k">ROLLBACK</span>;

<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
| id | name | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
|  <span class="pl-c1">1</span> | a    |  <span class="pl-c1">1000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span></pre></div>
<p>由于所有执行过的 SQL 语句都已经被提交过了，所以数据并没有发生回滚。那如何让数据可以发生回滚？</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 关闭自动提交</span>
<span class="pl-k">SET</span> AUTOCOMMIT <span class="pl-k">=</span> <span class="pl-c1">0</span>;

<span class="pl-c"><span class="pl-c">--</span> 查询自动提交状态</span>
<span class="pl-k">SELECT</span> @@AUTOCOMMIT;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------+</span>
| @@AUTOCOMMIT |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------+</span>
|            <span class="pl-c1">0</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------+</span></pre></div>
<p>将自动提交关闭后，测试数据回滚：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">INSERT INTO</span> user <span class="pl-k">VALUES</span> (<span class="pl-c1">2</span>, <span class="pl-s"><span class="pl-pds">'</span>b<span class="pl-pds">'</span></span>, <span class="pl-c1">1000</span>);

<span class="pl-c"><span class="pl-c">--</span> 关闭 AUTOCOMMIT 后，数据的变化是在一张虚拟的临时数据表中展示，</span>
<span class="pl-c"><span class="pl-c">--</span> 发生变化的数据并没有真正插入到数据表中。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
| id | name | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
|  <span class="pl-c1">1</span> | a    |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">2</span> | b    |  <span class="pl-c1">1000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>

<span class="pl-c"><span class="pl-c">--</span> 数据表中的真实数据其实还是：</span>
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
| id | name | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
|  <span class="pl-c1">1</span> | a    |  <span class="pl-c1">1000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>

<span class="pl-c"><span class="pl-c">--</span> 由于数据还没有真正提交，可以使用回滚</span>
<span class="pl-k">ROLLBACK</span>;

<span class="pl-c"><span class="pl-c">--</span> 再次查询</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
| id | name | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
|  <span class="pl-c1">1</span> | a    |  <span class="pl-c1">1000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span></pre></div>
<p>那如何将虚拟的数据真正提交到数据库中？使用 <code>COMMIT</code> :</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">INSERT INTO</span> user <span class="pl-k">VALUES</span> (<span class="pl-c1">2</span>, <span class="pl-s"><span class="pl-pds">'</span>b<span class="pl-pds">'</span></span>, <span class="pl-c1">1000</span>);
<span class="pl-c"><span class="pl-c">--</span> 手动提交数据（持久性），</span>
<span class="pl-c"><span class="pl-c">--</span> 将数据真正提交到数据库中，执行后不能再回滚提交过的数据。</span>
<span class="pl-k">COMMIT</span>;

<span class="pl-c"><span class="pl-c">--</span> 提交后测试回滚</span>
<span class="pl-k">ROLLBACK</span>;

<span class="pl-c"><span class="pl-c">--</span> 再次查询（回滚无效了）</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
| id | name | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
|  <span class="pl-c1">1</span> | a    |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">2</span> | b    |  <span class="pl-c1">1000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span></pre></div>
<blockquote>
<p><strong>总结</strong></p>
<ol>
<li>
<p><strong>自动提交</strong></p>
<ul>
<li>
<p>查看自动提交状态：<code>SELECT @@AUTOCOMMIT</code> ；</p>
</li>
<li>
<p>设置自动提交状态：<code>SET AUTOCOMMIT = 0</code> 。</p>
</li>
</ul>
</li>
<li>
<p><strong>手动提交</strong></p>
<p><code>@@AUTOCOMMIT = 0</code> 时，使用 <code>COMMIT</code> 命令提交事务。</p>
</li>
<li>
<p><strong>事务回滚</strong></p>
<p><code>@@AUTOCOMMIT = 0</code> 时，使用 <code>ROLLBACK</code> 命令回滚事务。</p>
</li>
</ol>
</blockquote>
<p><strong>事务的实际应用</strong>，让我们再回到银行转账项目：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 转账</span>
<span class="pl-k">UPDATE</span> user <span class="pl-k">set</span> <span class="pl-k">money</span> <span class="pl-k">=</span> <span class="pl-k">money</span> <span class="pl-k">-</span> <span class="pl-c1">100</span> <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>a<span class="pl-pds">'</span></span>;

<span class="pl-c"><span class="pl-c">--</span> 到账</span>
<span class="pl-k">UPDATE</span> user <span class="pl-k">set</span> <span class="pl-k">money</span> <span class="pl-k">=</span> <span class="pl-k">money</span> <span class="pl-k">+</span> <span class="pl-c1">100</span> <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>b<span class="pl-pds">'</span></span>;

<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
| id | name | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
|  <span class="pl-c1">1</span> | a    |   <span class="pl-c1">900</span> |
|  <span class="pl-c1">2</span> | b    |  <span class="pl-c1">1100</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span></pre></div>
<p>这时假设在转账时发生了意外，就可以使用 <code>ROLLBACK</code> 回滚到最后一次提交的状态：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 假设转账发生了意外，需要回滚。</span>
<span class="pl-k">ROLLBACK</span>;

<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
| id | name | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
|  <span class="pl-c1">1</span> | a    |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">2</span> | b    |  <span class="pl-c1">1000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span></pre></div>
<p>这时我们又回到了发生意外之前的状态，也就是说，事务给我们提供了一个可以反悔的机会。假设数据没有发生意外，这时可以手动将数据真正提交到数据表中：<code>COMMIT</code> 。</p>
<h3><a id="user-content-手动开启事务---begin--start-transaction" class="anchor" aria-hidden="true" href="#手动开启事务---begin--start-transaction"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>手动开启事务 - BEGIN / START TRANSACTION</h3>
<p>事务的默认提交被开启 ( <code>@@AUTOCOMMIT = 1</code> ) 后，此时就不能使用事务回滚了。但是我们还可以手动开启一个事务处理事件，使其可以发生回滚：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 使用 BEGIN 或者 START TRANSACTION 手动开启一个事务</span>
<span class="pl-c"><span class="pl-c">--</span> START TRANSACTION;</span>
<span class="pl-k">BEGIN</span>;
<span class="pl-k">UPDATE</span> user <span class="pl-k">set</span> <span class="pl-k">money</span> <span class="pl-k">=</span> <span class="pl-k">money</span> <span class="pl-k">-</span> <span class="pl-c1">100</span> <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>a<span class="pl-pds">'</span></span>;
<span class="pl-k">UPDATE</span> user <span class="pl-k">set</span> <span class="pl-k">money</span> <span class="pl-k">=</span> <span class="pl-k">money</span> <span class="pl-k">+</span> <span class="pl-c1">100</span> <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>b<span class="pl-pds">'</span></span>;

<span class="pl-c"><span class="pl-c">--</span> 由于手动开启的事务没有开启自动提交，</span>
<span class="pl-c"><span class="pl-c">--</span> 此时发生变化的数据仍然是被保存在一张临时表中。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
| id | name | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
|  <span class="pl-c1">1</span> | a    |   <span class="pl-c1">900</span> |
|  <span class="pl-c1">2</span> | b    |  <span class="pl-c1">1100</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>

<span class="pl-c"><span class="pl-c">--</span> 测试回滚</span>
<span class="pl-k">ROLLBACK</span>;

<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
| id | name | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
|  <span class="pl-c1">1</span> | a    |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">2</span> | b    |  <span class="pl-c1">1000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span></pre></div>
<p>仍然使用 <code>COMMIT</code> 提交数据，提交后无法再发生本次事务的回滚。</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">BEGIN</span>;
<span class="pl-k">UPDATE</span> user <span class="pl-k">set</span> <span class="pl-k">money</span> <span class="pl-k">=</span> <span class="pl-k">money</span> <span class="pl-k">-</span> <span class="pl-c1">100</span> <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>a<span class="pl-pds">'</span></span>;
<span class="pl-k">UPDATE</span> user <span class="pl-k">set</span> <span class="pl-k">money</span> <span class="pl-k">=</span> <span class="pl-k">money</span> <span class="pl-k">+</span> <span class="pl-c1">100</span> <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>b<span class="pl-pds">'</span></span>;

<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
| id | name | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>
|  <span class="pl-c1">1</span> | a    |   <span class="pl-c1">900</span> |
|  <span class="pl-c1">2</span> | b    |  <span class="pl-c1">1100</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+------+-------+</span>

<span class="pl-c"><span class="pl-c">--</span> 提交数据</span>
<span class="pl-k">COMMIT</span>;

<span class="pl-c"><span class="pl-c">--</span> 测试回滚（无效，因为表的数据已经被提交）</span>
<span class="pl-k">ROLLBACK</span>;</pre></div>
<h3><a id="user-content-事务的-acid-特征与使用" class="anchor" aria-hidden="true" href="#事务的-acid-特征与使用"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>事务的 ACID 特征与使用</h3>
<p><strong>事务的四大特征：</strong></p>
<ul>
<li><strong>A 原子性</strong>：事务是最小的单位，不可以再分割；</li>
<li><strong>C 一致性</strong>：要求同一事务中的 SQL 语句，必须保证同时成功或者失败；</li>
<li><strong>I 隔离性</strong>：事务1 和 事务2 之间是具有隔离性的；</li>
<li><strong>D 持久性</strong>：事务一旦结束 ( <code>COMMIT</code> ) ，就不可以再返回了 ( <code>ROLLBACK</code> ) 。</li>
</ul>
<h3><a id="user-content-事务的隔离性" class="anchor" aria-hidden="true" href="#事务的隔离性"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>事务的隔离性</h3>
<p><strong>事务的隔离性可分为四种 ( 性能从低到高 )</strong> ：</p>
<ol>
<li>
<p><strong>READ UNCOMMITTED ( 读取未提交 )</strong></p>
<p>如果有多个事务，那么任意事务都可以看见其他事务的<strong>未提交数据</strong>。</p>
</li>
<li>
<p><strong>READ COMMITTED ( 读取已提交 )</strong></p>
<p>只能读取到其他事务<strong>已经提交的数据</strong>。</p>
</li>
<li>
<p><strong>REPEATABLE READ ( 可被重复读 )</strong></p>
<p>如果有多个连接都开启了事务，那么事务之间不能共享数据记录，否则只能共享已提交的记录。</p>
</li>
<li>
<p><strong>SERIALIZABLE ( 串行化 )</strong></p>
<p>所有的事务都会按照<strong>固定顺序执行</strong>，执行完一个事务后再继续执行下一个事务的<strong>写入操作</strong>。</p>
</li>
</ol>
<p>查看当前数据库的默认隔离级别：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> MySQL 8.x, GLOBAL 表示系统级别，不加表示会话级别。</span>
<span class="pl-k">SELECT</span> @@<span class="pl-c1">GLOBAL</span>.<span class="pl-c1">TRANSACTION_ISOLATION</span>;
<span class="pl-k">SELECT</span> @@TRANSACTION_ISOLATION;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span>
| @@<span class="pl-c1">GLOBAL</span>.<span class="pl-c1">TRANSACTION_ISOLATION</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span>
| REPEATABLE<span class="pl-k">-</span>READ                | <span class="pl-c"><span class="pl-c">--</span> MySQL的默认隔离级别，可以重复读。</span>
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span>

<span class="pl-c"><span class="pl-c">--</span> MySQL 5.x</span>
<span class="pl-k">SELECT</span> @@<span class="pl-c1">GLOBAL</span>.<span class="pl-c1">TX_ISOLATION</span>;
<span class="pl-k">SELECT</span> @@TX_ISOLATION;</pre></div>
<p>修改隔离级别：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 设置系统隔离级别，LEVEL 后面表示要设置的隔离级别 (READ UNCOMMITTED)。</span>
<span class="pl-k">SET</span> GLOBAL TRANSACTION ISOLATION LEVEL READ UNCOMMITTED;

<span class="pl-c"><span class="pl-c">--</span> 查询系统隔离级别，发现已经被修改。</span>
<span class="pl-k">SELECT</span> @@<span class="pl-c1">GLOBAL</span>.<span class="pl-c1">TRANSACTION_ISOLATION</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span>
| @@<span class="pl-c1">GLOBAL</span>.<span class="pl-c1">TRANSACTION_ISOLATION</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span>
| READ<span class="pl-k">-</span>UNCOMMITTED               |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span></pre></div>
<h4><a id="user-content-脏读" class="anchor" aria-hidden="true" href="#脏读"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>脏读</h4>
<p>测试 <strong>READ UNCOMMITTED ( 读取未提交 )</strong> 的隔离性：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">INSERT INTO</span> user <span class="pl-k">VALUES</span> (<span class="pl-c1">3</span>, <span class="pl-s"><span class="pl-pds">'</span>小明<span class="pl-pds">'</span></span>, <span class="pl-c1">1000</span>);
<span class="pl-k">INSERT INTO</span> user <span class="pl-k">VALUES</span> (<span class="pl-c1">4</span>, <span class="pl-s"><span class="pl-pds">'</span>淘宝店<span class="pl-pds">'</span></span>, <span class="pl-c1">1000</span>);

<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
| id | name      | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
|  <span class="pl-c1">1</span> | a         |   <span class="pl-c1">900</span> |
|  <span class="pl-c1">2</span> | b         |  <span class="pl-c1">1100</span> |
|  <span class="pl-c1">3</span> | 小明      |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">4</span> | 淘宝店    |  <span class="pl-c1">1000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>

<span class="pl-c"><span class="pl-c">--</span> 开启一个事务操作数据</span>
<span class="pl-c"><span class="pl-c">--</span> 假设小明在淘宝店买了一双800块钱的鞋子：</span>
<span class="pl-k">START TRANSACTION</span>;
<span class="pl-k">UPDATE</span> user <span class="pl-k">SET</span> <span class="pl-k">money</span> <span class="pl-k">=</span> <span class="pl-k">money</span> <span class="pl-k">-</span> <span class="pl-c1">800</span> <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>小明<span class="pl-pds">'</span></span>;
<span class="pl-k">UPDATE</span> user <span class="pl-k">SET</span> <span class="pl-k">money</span> <span class="pl-k">=</span> <span class="pl-k">money</span> <span class="pl-k">+</span> <span class="pl-c1">800</span> <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>淘宝店<span class="pl-pds">'</span></span>;

<span class="pl-c"><span class="pl-c">--</span> 然后淘宝店在另一方查询结果，发现钱已到账。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
| id | name      | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
|  <span class="pl-c1">1</span> | a         |   <span class="pl-c1">900</span> |
|  <span class="pl-c1">2</span> | b         |  <span class="pl-c1">1100</span> |
|  <span class="pl-c1">3</span> | 小明      |   <span class="pl-c1">200</span> |
|  <span class="pl-c1">4</span> | 淘宝店    |  <span class="pl-c1">1800</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span></pre></div>
<p>由于小明的转账是在新开启的事务上进行操作的，而该操作的结果是可以被其他事务（另一方的淘宝店）看见的，因此淘宝店的查询结果是正确的，淘宝店确认到账。但就在这时，如果小明在它所处的事务上又执行了 <code>ROLLBACK</code> 命令，会发生什么？</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 小明所处的事务</span>
<span class="pl-k">ROLLBACK</span>;

<span class="pl-c"><span class="pl-c">--</span> 此时无论对方是谁，如果再去查询结果就会发现：</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
| id | name      | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
|  <span class="pl-c1">1</span> | a         |   <span class="pl-c1">900</span> |
|  <span class="pl-c1">2</span> | b         |  <span class="pl-c1">1100</span> |
|  <span class="pl-c1">3</span> | 小明      |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">4</span> | 淘宝店    |  <span class="pl-c1">1000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span></pre></div>
<p>这就是所谓的<strong>脏读</strong>，一个事务读取到另外一个事务还未提交的数据。这在实际开发中是不允许出现的。</p>
<h4><a id="user-content-读取已提交" class="anchor" aria-hidden="true" href="#读取已提交"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>读取已提交</h4>
<p>把隔离级别设置为 <strong>READ COMMITTED</strong> ：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SET</span> GLOBAL TRANSACTION ISOLATION LEVEL READ COMMITTED;
<span class="pl-k">SELECT</span> @@<span class="pl-c1">GLOBAL</span>.<span class="pl-c1">TRANSACTION_ISOLATION</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span>
| @@<span class="pl-c1">GLOBAL</span>.<span class="pl-c1">TRANSACTION_ISOLATION</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span>
| READ<span class="pl-k">-</span>COMMITTED                 |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span></pre></div>
<p>这样，再有新的事务连接进来时，它们就只能查询到已经提交过的事务数据了。但是对于当前事务来说，它们看到的还是未提交的数据，例如：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 正在操作数据事务（当前事务）</span>
<span class="pl-k">START TRANSACTION</span>;
<span class="pl-k">UPDATE</span> user <span class="pl-k">SET</span> <span class="pl-k">money</span> <span class="pl-k">=</span> <span class="pl-k">money</span> <span class="pl-k">-</span> <span class="pl-c1">800</span> <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>小明<span class="pl-pds">'</span></span>;
<span class="pl-k">UPDATE</span> user <span class="pl-k">SET</span> <span class="pl-k">money</span> <span class="pl-k">=</span> <span class="pl-k">money</span> <span class="pl-k">+</span> <span class="pl-c1">800</span> <span class="pl-k">WHERE</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>淘宝店<span class="pl-pds">'</span></span>;

<span class="pl-c"><span class="pl-c">--</span> 虽然隔离级别被设置为了 READ COMMITTED，但在当前事务中，</span>
<span class="pl-c"><span class="pl-c">--</span> 它看到的仍然是数据表中临时改变数据，而不是真正提交过的数据。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
| id | name      | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
|  <span class="pl-c1">1</span> | a         |   <span class="pl-c1">900</span> |
|  <span class="pl-c1">2</span> | b         |  <span class="pl-c1">1100</span> |
|  <span class="pl-c1">3</span> | 小明      |   <span class="pl-c1">200</span> |
|  <span class="pl-c1">4</span> | 淘宝店    |  <span class="pl-c1">1800</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>


<span class="pl-c"><span class="pl-c">--</span> 假设此时在远程开启了一个新事务，连接到数据库。</span>
$ mysql <span class="pl-k">-</span>u root <span class="pl-k">-</span>p12345612

<span class="pl-c"><span class="pl-c">--</span> 此时远程连接查询到的数据只能是已经提交过的</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
| id | name      | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
|  <span class="pl-c1">1</span> | a         |   <span class="pl-c1">900</span> |
|  <span class="pl-c1">2</span> | b         |  <span class="pl-c1">1100</span> |
|  <span class="pl-c1">3</span> | 小明      |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">4</span> | 淘宝店    |  <span class="pl-c1">1000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span></pre></div>
<p>但是这样还有问题，那就是假设一个事务在操作数据时，其他事务干扰了这个事务的数据。例如：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 小张在查询数据的时候发现：</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
| id | name      | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
|  <span class="pl-c1">1</span> | a         |   <span class="pl-c1">900</span> |
|  <span class="pl-c1">2</span> | b         |  <span class="pl-c1">1100</span> |
|  <span class="pl-c1">3</span> | 小明      |   <span class="pl-c1">200</span> |
|  <span class="pl-c1">4</span> | 淘宝店    |  <span class="pl-c1">1800</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>

<span class="pl-c"><span class="pl-c">--</span> 在小张求表的 money 平均值之前，小王做了一个操作：</span>
<span class="pl-k">START TRANSACTION</span>;
<span class="pl-k">INSERT INTO</span> user <span class="pl-k">VALUES</span> (<span class="pl-c1">5</span>, <span class="pl-s"><span class="pl-pds">'</span>c<span class="pl-pds">'</span></span>, <span class="pl-c1">100</span>);
<span class="pl-k">COMMIT</span>;

<span class="pl-c"><span class="pl-c">--</span> 此时表的真实数据是：</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
| id | name      | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
|  <span class="pl-c1">1</span> | a         |   <span class="pl-c1">900</span> |
|  <span class="pl-c1">2</span> | b         |  <span class="pl-c1">1100</span> |
|  <span class="pl-c1">3</span> | 小明      |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">4</span> | 淘宝店    |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">5</span> | c         |   <span class="pl-c1">100</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>

<span class="pl-c"><span class="pl-c">--</span> 这时小张再求平均值的时候，就会出现计算不相符合的情况：</span>
<span class="pl-k">SELECT</span> <span class="pl-c1">AVG</span>(<span class="pl-k">money</span>) <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----------+</span>
| <span class="pl-c1">AVG</span>(<span class="pl-k">money</span>) |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----------+</span>
|  <span class="pl-c1">820</span>.<span class="pl-c1">0000</span>  |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>----------+</span></pre></div>
<p>虽然 <strong>READ COMMITTED</strong> 让我们只能读取到其他事务已经提交的数据，但还是会出现问题，就是<strong>在读取同一个表的数据时，可能会发生前后不一致的情况。<strong>这被称为</strong>不可重复读现象 ( READ COMMITTED )</strong> 。</p>
<h4><a id="user-content-幻读" class="anchor" aria-hidden="true" href="#幻读"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>幻读</h4>
<p>将隔离级别设置为 <strong>REPEATABLE READ ( 可被重复读取 )</strong> :</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SET</span> GLOBAL TRANSACTION ISOLATION LEVEL REPEATABLE READ;
<span class="pl-k">SELECT</span> @@<span class="pl-c1">GLOBAL</span>.<span class="pl-c1">TRANSACTION_ISOLATION</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span>
| @@<span class="pl-c1">GLOBAL</span>.<span class="pl-c1">TRANSACTION_ISOLATION</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span>
| REPEATABLE<span class="pl-k">-</span>READ                |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span></pre></div>
<p>测试 <strong>REPEATABLE READ</strong> ，假设在两个不同的连接上分别执行 <code>START TRANSACTION</code> :</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 小张 - 成都</span>
<span class="pl-k">START TRANSACTION</span>;
<span class="pl-k">INSERT INTO</span> user <span class="pl-k">VALUES</span> (<span class="pl-c1">6</span>, <span class="pl-s"><span class="pl-pds">'</span>d<span class="pl-pds">'</span></span>, <span class="pl-c1">1000</span>);

<span class="pl-c"><span class="pl-c">--</span> 小王 - 北京</span>
<span class="pl-k">START TRANSACTION</span>;

<span class="pl-c"><span class="pl-c">--</span> 小张 - 成都</span>
<span class="pl-k">COMMIT</span>;</pre></div>
<p>当前事务开启后，没提交之前，查询不到，提交后可以被查询到。但是，在提交之前其他事务被开启了，那么在这条事务线上，就不会查询到当前有操作事务的连接。相当于开辟出一条单独的线程。</p>
<p>无论小张是否执行过 <code>COMMIT</code> ，在小王这边，都不会查询到小张的事务记录，而是只会查询到自己所处事务的记录：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
| id | name      | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
|  <span class="pl-c1">1</span> | a         |   <span class="pl-c1">900</span> |
|  <span class="pl-c1">2</span> | b         |  <span class="pl-c1">1100</span> |
|  <span class="pl-c1">3</span> | 小明      |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">4</span> | 淘宝店    |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">5</span> | c         |   <span class="pl-c1">100</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span></pre></div>
<p>这是<strong>因为小王在此之前开启了一个新的事务 ( <code>START TRANSACTION</code> ) <strong>，那么</strong>在他的这条新事务的线上，跟其他事务是没有联系的</strong>，也就是说，此时如果其他事务正在操作数据，它是不知道的。</p>
<p>然而事实是，在真实的数据表中，小张已经插入了一条数据。但是小王此时并不知道，也插入了同一条数据，会发生什么呢？</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">INSERT INTO</span> user <span class="pl-k">VALUES</span> (<span class="pl-c1">6</span>, <span class="pl-s"><span class="pl-pds">'</span>d<span class="pl-pds">'</span></span>, <span class="pl-c1">1000</span>);
<span class="pl-c"><span class="pl-c">--</span> ERROR 1062 (23000): Duplicate entry '6' for key 'PRIMARY'</span></pre></div>
<p>报错了，操作被告知已存在主键为 <code>6</code> 的字段。这种现象也被称为<strong>幻读，一个事务提交的数据，不能被其他事务读取到</strong>。</p>
<h4><a id="user-content-串行化" class="anchor" aria-hidden="true" href="#串行化"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>串行化</h4>
<p>顾名思义，就是所有事务的<strong>写入操作</strong>全都是串行化的。什么意思？把隔离级别修改成 <strong>SERIALIZABLE</strong> :</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-k">SET</span> GLOBAL TRANSACTION ISOLATION LEVEL SERIALIZABLE;
<span class="pl-k">SELECT</span> @@<span class="pl-c1">GLOBAL</span>.<span class="pl-c1">TRANSACTION_ISOLATION</span>;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span>
| @@<span class="pl-c1">GLOBAL</span>.<span class="pl-c1">TRANSACTION_ISOLATION</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span>
| SERIALIZABLE                   |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>------------------------------+</span></pre></div>
<p>还是拿小张和小王来举例：</p>
<div class="highlight highlight-source-sql"><pre><span class="pl-c"><span class="pl-c">--</span> 小张 - 成都</span>
<span class="pl-k">START TRANSACTION</span>;

<span class="pl-c"><span class="pl-c">--</span> 小王 - 北京</span>
<span class="pl-k">START TRANSACTION</span>;

<span class="pl-c"><span class="pl-c">--</span> 开启事务之前先查询表，准备操作数据。</span>
<span class="pl-k">SELECT</span> <span class="pl-k">*</span> <span class="pl-k">FROM</span> user;
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
| id | name      | <span class="pl-k">money</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>
|  <span class="pl-c1">1</span> | a         |   <span class="pl-c1">900</span> |
|  <span class="pl-c1">2</span> | b         |  <span class="pl-c1">1100</span> |
|  <span class="pl-c1">3</span> | 小明      |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">4</span> | 淘宝店    |  <span class="pl-c1">1000</span> |
|  <span class="pl-c1">5</span> | c         |   <span class="pl-c1">100</span> |
|  <span class="pl-c1">6</span> | d         |  <span class="pl-c1">1000</span> |
<span class="pl-k">+</span><span class="pl-c"><span class="pl-c">--</span>--+-----------+-------+</span>

<span class="pl-c"><span class="pl-c">--</span> 发现没有 7 号王小花，于是插入一条数据：</span>
<span class="pl-k">INSERT INTO</span> user <span class="pl-k">VALUES</span> (<span class="pl-c1">7</span>, <span class="pl-s"><span class="pl-pds">'</span>王小花<span class="pl-pds">'</span></span>, <span class="pl-c1">1000</span>);</pre></div>
<p>此时会发生什么呢？由于现在的隔离级别是 <strong>SERIALIZABLE ( 串行化 )</strong> ，串行化的意思就是：假设把所有的事务都放在一个串行的队列中，那么所有的事务都会按照<strong>固定顺序执行</strong>，执行完一个事务后再继续执行下一个事务的<strong>写入操作</strong> ( <strong>这意味着队列中同时只能执行一个事务的写入操作</strong> ) 。</p>
<p>根据这个解释，小王在插入数据时，会出现等待状态，直到小张执行 <code>COMMIT</code> 结束它所处的事务，或者出现等待超时。</p>
