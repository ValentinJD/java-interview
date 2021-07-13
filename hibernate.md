## Ответы
### 1. Что такое Hibernate Framework?
   Hibernate — библиотека для языка программирования Java, предназначенная для решения задач объектно-реляционного отображения (object-relational mapping — ORM). Она представляет собой свободное программное обеспечение с открытым исходным кодом (open source), распространяемое на условиях GNU Lesser General Public License. Данная библиотека предоставляет легкий в использовании каркас (фреймворк) для отображения объектно-ориентированной модели данных в традиционные реляционные базы данных. Hibernate совместима с JSR-220/317 и предоставляет стандартные средства JPA.

### 2. Какие важные преимущества дает использование Hibernate Framework?
Hibernate является одним из самых востребованных ORM фреймворков для Java. И вот почему:

+ Hibernate устраняет множество спагетти кода (повторяющегося), который постоянно преследует разработчика при работе с JDBC. Скрывает от разработчика множество кода, необходимого для управления ресурсами и позволяет сосредоточиться на бизнес логике.
+ Hibernate поддерживает XML так же как и JPA аннотации, что позволяет сделать реализацию кода независимой.
+ Hibernate предоставляет собственный мощный язык запросов (HQL), который похож на SQL. Стоит отметить, что HQL полностью объектно-ориентирован и понимает такие принципы, как наследование, полиморфизм и ассоциации (связи).
+ Hibernate – широко распространенный open source проект. Благодаря этому доступны тысячи открытых статей, примеров, а так же документации по использованию фреймворка.
+ Hibernate легко интегрируется с другими Java EE фреймворками, например, Spring Framework поддерживает встроенную интеграцию с Hibernate.
+ Hibernate поддерживает ленивую инициализацию используя proxy объекты и выполняет запросы к базе данных только по необходимости. 
+ Hibernate поддерживает разные уровни cache, а следовательно может повысить производительность.
+ Важно, что Hibernate может использовать чистый SQL, а значит поддерживает возможность оптимизации запросов и работы с любым сторонним вендором БД и его фичами.
### 3. Какие преимущества Hibernate над JDBC?
   Hibernate имеет ряд преимуществ перед JDBC API:

Hibernate удаляет множество повторяющегося кода из JDBC API, а следовательно его легче читать, писать и поддерживать.
Hibernate поддерживает наследование, ассоциации и коллекции, что не доступно в JDBC API.
Hibernate неявно использует управление транзакциями. Большинство запросов нельзя выполнить вне транзакции. При использовании JDBC API для управления транзакциями нужно явно использовать commit и rollback.
JDBC API throws SQLException, которое относится к проверяемым исключениям, а значит необходимо постоянно писать множество блоков try-catch. В большинстве случаев это не нужно для каждого вызова JDBC и используется для управления транзакциями. Hibernate оборачивает исключения JDBC через непроверяемые JDBCException или HibernateException, а значит нет необходимости проверять их в коде каждый раз. Встроенная поддержка управления транзакциями в Hibernate убирает блоки try-catch.
Hibernate Query Language (HQL) более объектно ориентированный и близкий к Java язык запросов, чем SQL в JDBC.
Hibernate поддерживает кэширование, а запросы JDBC – нет, что может понизить производительность.
Конфигурация Hibernate позволяет использовать JDBC вроде соединения по типу JNDI DataSource для пула соединений. Это важная фича для энтерпрайз приложений, которая полностью отсутствует в JDBC API.
Hibernate поддерживает аннотации JPA, а значит код является переносимым на другие ORM фреймворки, реализующие стандарт, в то время как код JDBC сильно привязан к приложению.
### 4. Назовите некоторые важные интерфейсы Hibernate.
   SessionFactory (org.hibernate.SessionFactory) – неизменяемый потокобезопасный объект с компилированным маппингом для одной базы данных. Необходимо инициализировать SessionFactory всего один раз. Экземпляр SessionFactory используется для получения объектов Session, которые используются для операций с базами данных.
   Session (org.hibernate.Session) – однопоточный короткоживущий объект, который предоставляет связь между объектами приложения и базой данных. Он оборачивает JDBC java.sql.Connection и работает как фабрика для org.hibernate.Transaction. Разработчик должен открывать сессию по необходимости и закрывать ее сразу после использования. Экземпляр Session является интерфейсом между кодом в java приложении и hibernate framework и предоставляет методы для операций CRUD.
   Transaction (org.hibernate.Transaction) – однопоточный короткоживущий объект, используемый для атомарных операций. Это абстракция приложения от основных JDBC или JTA транзакций. org.hibernate.Session может занимать несколько org.hibernate.Transaction в определенных случаях.
### 5. Что такое конфигурационный файл Hibernate?
   Файл конфигурации Hibernate содержит в себе данные о базе данных и необходим для инициализации SessionFactory. В .xml файле необходимо указать вендора базы данных или JNDI ресурсы, а так же информацию об используемом диалекте, что поможет hibernate выбрать режим работы с конкретной базой данных.

### 6. Что такое Hibernate mapping file?
   Файл отображения (mapping file) используется для связи entity бинов и колонок в таблице базы данных. В случаях, когда не используются аннотации JPA, файл отображения .xml может быть полезен (например при использовании сторонних библиотек).

### 7. Назовите некоторые важные аннотации, используемые для отображения в Hibernate.
   Hibernate поддерживает как аннотации из JPA, так и свои собственные, которые находятся в пакете org.hibernate.annotations. Наиболее важные аннотации JPA и Hibernate:

javax.persistence.Entity: используется для указания класса как entity bean.
javax.persistence.Table: используется для определения имени таблицы из БД, которая будет отображаться на entity bean.
javax.persistence.Access: определяет тип доступа, поле или свойство. Поле – является значением по умолчанию и если нужно, чтобы hibernate использовал методы getter/setter, то их необходимо задать для нужного свойства.
javax.persistence.Id: определяет primary key в entity bean.
javax.persistence.EmbeddedId: используется для определения составного ключа в бине.
javax.persistence.Column: определяет имя колонки из таблицы в базе данных.
javax.persistence.GeneratedValue: задает стратегию создания основных ключей. Используется в сочетании с javax.persistence.GenerationType enum.
javax.persistence.OneToOne: задает связь один-к-одному между двумя сущностными бинами. Соответственно есть другие аннотации OneToMany, ManyToOne и ManyToMany.
org.hibernate.annotations.Cascade: определяет каскадную связь между двумя entity бинами. Используется в связке с org.hibernate.annotations.CascadeType.
javax.persistence.PrimaryKeyJoinColumn: определяет внешний ключ для свойства. Используется вместе с org.hibernate.annotations.GenericGenerator и org.hibernate.annotations.Parameter.
### 8. Что вы знаете о Hibernate SessionFactory и как его сконфигурировать?
   SessionFactory является фабрикой классов и используется для получения объектов session. SessionFactory отвечает за считывание параметров конфигурации Hibernate и подключение к базе данных. Обычно в приложении имеется только один экземпляр SessionFactory и потоки, обслуживающие клиентские запросы, получают экземпляры session с помощью объекта SessionFactory. Внутреннее состояние SessionFactory неизменно (immutable). Internal state (внутреннее состояние) включает в себя все метаданные об Object/ Relational Mapping и задается при создании SessionFactory.

SessionFactory также предоставляет методы для получения метаданных класса и статистики, вроде данных о втором уровне кэша, выполняемых запросах и т.д.

### 9. Является ли Hibernate SessionFactory потокобезопасным?
   Т.к. объект SessionFactory immutable (неизменяемый), то да, он потокобезопасный. Множество потоков может обращаться к одному объекту одновременно.

### 10. Как получить Hibernate Session и что это такое?
    Объект Hibernate Session является связью между кодом java приложения и hibernate. Это основной интерфейс для выполнения операций с базой данных. Жизненный цикл объекта session связан с началом и окончанием транзакции. Этот объект предоставляет методы для CRUD (create, read, update, delete) операций для объекта персистентности. С помощью этого экземпляра можно выполнять HQL, SQL запросы и задавать критерии выборки.

### 11. Является ли Hibernate Session потокобезопасным?
    Объект Hibernate Session не является потокобезопасным. Каждый поток должен иметь свой собственный объект Session и закрывать его по окончанию.

### 12. В чем разница между openSession и getCurrentSession?
    Hibernate SessionFactory getCurrentSession() возвращает сессию, связанную с контекстом. Но для того, чтобы это работало, нам нужно настроить его в конфигурационном файле hibernate. Так как этот объект session связан с контекстом hibernate, то отпадает необходимость к его закрытию. Объект session закрывается вместе с закрытием SessionFactory.

<property name="hibernate.current_session_context_class">thread</property>
1
<property name="hibernate.current_session_context_class">thread</property>
Метод Hibernate SessionFactory openSession() всегда создает новую сессию. Мы должны обязательно контролировать закрытие объекта сеанса по завершению всех операций с базой данных. Для многопоточной среды необходимо создавать новый объект session для каждого запроса.

Существует еще один метод openStatelessSession(), который возвращает session без поддержки состояния. Такой объект не реализует первый уровень кэширования и не взаимодействует с вторым уровнем. Сюда же можно отнести игнорирование коллекций и некоторых обработчиков событий. Такие объекты могут быть полезны при загрузке больших объемов данных без удержания большого кол-ва информации в кэше.

### 13. Какая разница между методами Hibernate Session get() и load()?
    Hibernate session обладает различными методами для загрузки данных из базы данных. Наиболее часто используемые методы для этого – get() и load().

get() загружает данные сразу при вызове, в то время как load() использует прокси объект и загружает данные только тогда, когда это требуется на самом деле. В этом плане load() имеет преимущество в плане ленивой загрузки данных.
load() бросает исключение, когда данные не найдены. Поэтому его нужно использовать только при уверенности в существовании данных.
Нужно использовать метод get(), если необходимо удостовериться в наличии данных в БД.
### 14. Что вы знаете о кэшировании в Hibernate? Объясните понятие кэш первого уровня в Hibernate?
    Hibernate использует кэширование, чтобы сделать наше приложение быстрее. Кэш Hibernate может быть очень полезным в получении высокой производительности приложения при правильном использовании. Идея кэширования заключается в сокращении количества запросов к базе данных.

Кэш первого уровня Hibernate связан с объектом Session. Кэш первого уровня у Hibernate  включен по умолчанию и не существует никакого способа, чтобы его отключить. Однако Hibernate предоставляет методы, с помощью которых мы можем удалить выбранные объекты из кэша или полностью очистить кэш.
Любой объект закэшированный в session не будет виден другим объектам session. После закрытия объекта сессии все кэшированные объекты будут потеряны.

### 15. Как настроить кэш второго уровня в Hibernate с помощью EHCache?
    EHCache является лучшим выбором для организации кэширования второго уровня в хибернейт. Для настройки второго уровня кэширования в хибернейт требуется выполнить несколько шагов.

Добавить зависимость hibernate-ehcache в проект.
<dependency>
<groupId>org.hibernate</groupId>
<artifactId>hibernate-ehcache</artifactId>
<version>4.3.5.Final</version>
</dependency>
<dependency>
<groupId>org.hibernate</groupId>
<artifactId>hibernate-ehcache</artifactId>
<version>4.3.5.Final</version>
</dependency>
Добавить несколько записей в конфигурационный файл Hibernate.
<property name="hibernate.cache.region.factory_class">org.hibernate.cache.ehcache.EhCacheRegionFactory</property>

<!-- For singleton factory -->
<!-- <property name="hibernate.cache.region.factory_class">org.hibernate.cache.ehcache.SingletonEhCacheRegionFactory</property>
-->

<!-- enable second level cache and query cache -->
<property name="hibernate.cache.use_second_level_cache">true</property>
<property name="hibernate.cache.use_query_cache">true</property>
<property name="net.sf.ehcache.configurationResourceName">/myehcache.xml</property>

<property name="hibernate.cache.region.factory_class">org.hibernate.cache.ehcache.EhCacheRegionFactory</property>

<!-- For singleton factory -->
<!-- <property name="hibernate.cache.region.factory_class">org.hibernate.cache.ehcache.SingletonEhCacheRegionFactory</property>
-->

<!-- enable second level cache and query cache -->
<property name="hibernate.cache.use_second_level_cache">true</property>
<property name="hibernate.cache.use_query_cache">true</property>
<property name="net.sf.ehcache.configurationResourceName">/myehcache.xml</property>
Создать файл конфигурации EHCache.
<?xml version="1.0" encoding="UTF-8"?>
<ehcache xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="ehcache.xsd" updateCheck="true"
monitoring="autodetect" dynamicConfig="true">

    <diskStore path="java.io.tmpdir/ehcache" />
  
    <defaultCache maxEntriesLocalHeap="10000" eternal="false"
        timeToIdleSeconds="120" timeToLiveSeconds="120" diskSpoolBufferSizeMB="30"
        maxEntriesLocalDisk="10000000" diskExpiryThreadIntervalSeconds="120"
        memoryStoreEvictionPolicy="LRU" statistics="true">
        <persistence strategy="localTempSwap" />
    </defaultCache>
  
    <cache name="employee" maxEntriesLocalHeap="10000" eternal="false"
        timeToIdleSeconds="5" timeToLiveSeconds="10">
        <persistence strategy="localTempSwap" />
    </cache>
  
    <cache name="org.hibernate.cache.internal.StandardQueryCache"
        maxEntriesLocalHeap="5" eternal="false" timeToLiveSeconds="120">
        <persistence strategy="localTempSwap" />
    </cache>
  
    <cache name="org.hibernate.cache.spi.UpdateTimestampsCache"
        maxEntriesLocalHeap="5000" eternal="true">
        <persistence strategy="localTempSwap" />
    </cache>
</ehcache>

<?xml version="1.0" encoding="UTF-8"?>
<ehcache xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:noNamespaceSchemaLocation="ehcache.xsd" updateCheck="true"
    monitoring="autodetect" dynamicConfig="true">

    <diskStore path="java.io.tmpdir/ehcache" />
  
    <defaultCache maxEntriesLocalHeap="10000" eternal="false"
        timeToIdleSeconds="120" timeToLiveSeconds="120" diskSpoolBufferSizeMB="30"
        maxEntriesLocalDisk="10000000" diskExpiryThreadIntervalSeconds="120"
        memoryStoreEvictionPolicy="LRU" statistics="true">
        <persistence strategy="localTempSwap" />
    </defaultCache>
  
    <cache name="employee" maxEntriesLocalHeap="10000" eternal="false"
        timeToIdleSeconds="5" timeToLiveSeconds="10">
        <persistence strategy="localTempSwap" />
    </cache>
  
    <cache name="org.hibernate.cache.internal.StandardQueryCache"
        maxEntriesLocalHeap="5" eternal="false" timeToLiveSeconds="120">
        <persistence strategy="localTempSwap" />
    </cache>
  
    <cache name="org.hibernate.cache.spi.UpdateTimestampsCache"
        maxEntriesLocalHeap="5000" eternal="true">
        <persistence strategy="localTempSwap" />
    </cache>
</ehcache>

Использовать аннотацию @Cache и указание настройки стратегии кэширование над entity bean.
import org.hibernate.annotations.Cache;
import org.hibernate.annotations.CacheConcurrencyStrategy;

@Entity
@Table(name = "ADDRESS")
@Cache(usage=CacheConcurrencyStrategy.READ_ONLY, region="employee")
public class Address {
}

import org.hibernate.annotations.Cache;
import org.hibernate.annotations.CacheConcurrencyStrategy;

@Entity
@Table(name = "ADDRESS")
@Cache(usage=CacheConcurrencyStrategy.READ_ONLY, region="employee")
public class Address {

}

### 16. Какие существуют различные состояния у entity bean?
    Transient: состояние, при котором объект никогда не был связан с какой-либо сессией и не является персистентностью. Этот объект находится во временном состоянии. Объект в этом состоянии может стать персистентным при вызове метода save(), persist() или saveOrUpdate(). Объект персистентности может перейти в transient состоянии после вызова метода delete().
    Persistent: когда объект связан с уникальной сессией он находится в состоянии persistent (персистентности). Любой экземпляр, возвращаемый методами get() или load() находится в состоянии persistent.
    Detached: если объект был персистентным, но сейчас не связан с какой-либо сессией, то он находится в отвязанном (detached) состоянии. Такой объект можно сделать персистентным используя методы update(), saveOrUpdate(), lock() или replicate(). Состояния transient или detached так же могут перейти в состояние persistent как новый объект персистентности после вызова метода merge().
### 17. Как используется вызов метода Hibernate Session merge()?
    Hibernate merge() может быть использован для обновления существующих значений, однако этот метод создает копию из переданного объекта сущности и возвращает его. Возвращаемый объект является частью контекста персистентности и отслеживает любые изменения, а переданный объект не отслеживается.

### 18. В чем разница между Hibernate save(), saveOrUpdate() и persist()?
    Hibernate save() используется для сохранения сущности в базу данных. Проблема с использованием метода save() заключается в том, что он может быть вызван без транзакции. А следовательно если у нас имеется отображение нескольких объектов, то только первичный объект будет сохранен и мы получим несогласованные данные. Также save() немедленно возвращает сгенерированный идентификатор.

Hibernate persist() аналогичен save() с транзакцией. persist() не возвращает сгенерированный идентификатор сразу.

Hibernate saveOrUpdate() использует запрос для вставки или обновления, основываясь на предоставленных данных. Если данные уже присутствуют в базе данных, то будет выполнен запрос обновления. Метод saveOrUpdate() можно применять без транзакции, но это может привести к аналогичным проблемам, как и в случае с методом save().

### 19. Что произойдет, если будет отсутствовать конструктор без аргументов у Entity Bean?
    Hibernate использует рефлексию для создания экземпляров Entity бинов при вызове методов get() или load(). Для этого используется метод Class.newInstance(), который требует наличия конструктора без параметров. Поэтому, в случае его отсутствия, вы получите ошибку HibernateException.

### 20. В чем разница между sorted collection и ordered collection? Какая из них лучше?
    При использовании алгоритмов сортировки из Collection API для сортировки коллекции используется сортированный список (sorted list). Для маленьких коллекций это не приводит к излишнему расходу ресурсов, но на больших коллекциях это может привести к потере производительности и ошибкам OutOfMemory. Так же entity бины должны реализовывать интерфейс Comparable или Comparator для работы с сортированными коллекциями.

При использовании фреймворка Hibernate для загрузки данных из базы данных мы можем применить Criteria API и команду order by для получения отсортированного списка (ordered list). Ordered list является лучшим выбором к sorted list, т.к. он использует сортировку на уровне базы данных. Она быстрее и не может привести к утечке памяти. Пример запроса к БД для получения ordered list:

List<Employee> empList = session.createCriteria(Employee.class)
.addOrder(Order.desc("id")).list();
1
2
List<Employee> empList = session.createCriteria(Employee.class)
.addOrder(Order.desc("id")).list();
### 21. Какие типы коллекций в Hibernate вы знаете?
    Bag
    Set
    List
    Array
    Map
### 22. Как реализованы Join’ы Hibernate?
    Существует несколько способов реализовать связи в Hibernate.

Использовать ассоциации, такие как one-to-one, one-to-many, many-to-many.
Использовать в HQL запросе команду JOIN. Существует другая форма “join fetch“, позволяющая загружать данные немедленно (не lazy).
Использовать чистый SQL запрос с командой join.
### 23. Почему мы не должны делать Entity class как final?
    Хибернейт использует прокси классы для ленивой загрузки данных (т.е. по необходимости, а не сразу). Это достигается с помощью расширения entity bean и, следовательно, если бы он был final, то это было бы невозможно. Ленивая загрузка данных во многих случаях повышает производительность, а следовательно важна.

### 24. Что вы знаете о HQL и какие его преимущества?
    Hibernate Framework поставляется с мощным объектно-ориентированным языком запросов – Hibernate Query Language (HQL). Он очень похож на SQL, за исключением, что в нем используются объекты вместо имен таблиц, что делает язык ближе к объектно-ориентированному программированию.

HQL является регистронезависимым, кроме использования в запросах имен java переменных и классов, где он подчиняется правилам Java. Например, SelECt то же самое, что и select, но ru.javastudy.MyClass отличен от  ru.javastudy.MyCLASS. Запросы HQL кэшируются (это как плюс так и минус).

Подробнее можете посмотреть в Hibernate — Hibernate Query (HQL) примеры: SELECT, INSERT, UPDATE, DELETE и в общем разделе Hibernate.

### 25. Что такое Query Cache в Hibernate?
    Hibernate реализует область кэша для запросов resultset, который тесно взаимодействует с кэшем второго уровня Hibernate. Для подключения этой дополнительной функции требуется несколько дополнительных шагов в коде. Query Cache полезны только для часто выполняющихся запросов с повторяющимися параметрами. Для начала необходимо добавить эту запись в файле конфигурации Hibernate:

<property name="hibernate.cache.use_query_cache">true</property>
1
<property name="hibernate.cache.use_query_cache">true</property>
Уже внутри кода приложения для запроса применяется метод setCacheable(true), как показано ниже:

Query query = session.createQuery("from Employee");
query.setCacheable(true);
query.setCacheRegion("ALL_EMP");
1
2
3
Query query = session.createQuery("from Employee");
query.setCacheable(true);
query.setCacheRegion("ALL_EMP");
### 26. Можем ли мы выполнить нативный запрос SQL (sql native) в Hibernate?
    С помощью использования SQLQuery можно выполнять чистый запрос SQL. В общем случае это не рекомендуется, т.к. вы потеряете все преимущества HQL (ассоциации, кэширование). Выполнить можно примерно так:

Transaction tx = session.beginTransaction();
SQLQuery query = session.createSQLQuery("select emp_id, emp_name, emp_salary from Employee");
List<Object[]> rows = query.list();
for(Object[] row : rows){
Employee emp = new Employee();
emp.setId(Long.parseLong(row[0].toString()));
emp.setName(row[1].toString());
emp.setSalary(Double.parseDouble(row[2].toString()));
System.out.println(emp);
}

Transaction tx = session.beginTransaction();
SQLQuery query = session.createSQLQuery("select emp_id, emp_name, emp_salary from Employee");
List<Object[]> rows = query.list();
for(Object[] row : rows){
Employee emp = new Employee();
emp.setId(Long.parseLong(row[0].toString()));
emp.setName(row[1].toString());
emp.setSalary(Double.parseDouble(row[2].toString()));
System.out.println(emp);
}

### 27. Назовите преимущества поддержки нативного sql в Hibernate.
    Использование нативного SQL может быть необходимо при выполнении запросов к некоторым базам данных, которые могут не поддерживаться в Hibernate. Примером может служить некоторые специфичные запросы и “фишки” при работе с БД от Oracle.

### 28. Что такое Named SQL Query?
    Hibernate поддерживает именованный запрос, который мы можем задать в каком-либо центральном месте и потом использовать его в любом месте в коде. Именованные запросы поддерживают как HQL, так и Native SQL. Создать именованный запрос можно с помощью JPA аннотаций @NamedQuery, @NamedNativeQuery или в конфигурационном файле отображения (mapping files).

Hibernate — примеры именованных запросов NamedQuery.

### 29. Какие преимущества Named SQL Query?
    Именованный запрос Hibernate позволяет собрать множество запросов в одном месте, а затем вызывать их в любом классе. Синтаксис Named Query проверяется при создании session factory, что позволяет заметить ошибку на раннем этапе, а не при запущенном приложении и выполнении запроса. Named Query глобальные, т.е. заданные однажды, могут быть использованы в любом месте.

Однако одним из основных недостатков именованного запроса является то, что его очень трудно отлаживать (могут быть сложности с поиском места определения запроса).

### 30. Расскажите о преимуществах использования Hibernate Criteria API.
    Hibernate Criteria API является более объектно-ориентированным для запросов, которые получают результат из базы данных. Для операций update, delete или других DDL манипуляций использовать Criteria API нельзя. Критерии используются только для выборки из базы данных в более объектно-ориентированном стиле.

Вот некоторые области применения Criteria API:

Criteria API поддерживает проекцию, которую мы можем использовать для агрегатных функций вроде sum(), min(), max() и т.д.
Criteria API может использовать ProjectionList для извлечения данных только из выбранных колонок.
Criteria API может быть использована для join запросов с помощью соединения нескольких таблиц, используя методы createAlias(), setFetchMode() и setProjection().
Criteria API поддерживает выборку результатов согласно условиям (ограничениям). Для этого используется метод add() с помощью которого добавляются ограничения (Restrictions).
Criteria API позволяет добавлять порядок (сортировку) к результату с помощью метода addOrder().

### 31. Как логировать созданные Hibernate SQL запросы в лог-файлы?
    Для логирования запросов SQL добавьте в файл конфигурации Hibernate строчку:

<property name="hibernate.show_sql">true</property>
1
<property name="hibernate.show_sql">true</property>
Отметьте, что это необходимо использовать на уровне Development или Testing и должно быть отключено в продакшн.

### 32. Что вы знаете о Hibernate прокси и как это помогает в ленивой загрузке (lazy load)?
    Hibernate использует прокси объект для поддержки отложенной загрузки. Обычно при загрузке данных из таблицы Hibernate не загружает все отображенные (замаппинные) объекты. Как только вы ссылаетесь на дочерний объект или ищите объект с помощью геттера, если связанная сущность не находиться в кэше сессии, то прокси код перейдет к базе данных для загрузки связанной сущности. Для этого используется javassist, чтобы эффективно и динамически создавать реализации подклассов ваших entity объектов.

### 33. Как реализованы отношения в Hibernate?
    Реализовать отношение one-to-one, one-to-many, many-to-many можно с помощью JPA аннотаций или конфигурирования xml файла. За примерами посетите раздел Hibernate.

### 34. Как управлять транзакциями с помощью Hibernate?
    Hibernate вообще не допускает большинство операций без использования транзакций. Поэтому после получения экземпляра session от SessionFactory необходимо выполнить beginTransaction() для начала транзакции. Метод вернет ссылку, которую мы можем использовать для подтверждения или отката транзакции.

В целом, управление транзакциями в фреймворке выполнено гораздо лучше, чем в JDBC, т.к. мы не должны полагаться на возникновение исключения для отката транзакции. Любое исключение автоматически вызовет rollback.

### 35. Что такое каскадные связи (обновления) и какие каскадные типы есть в Hibernate?
    Если у нас имеются зависимости между сущностями (entities), то нам необходимо определить как различные операции будут влиять на другую сущность. Это реализуется с помощью каскадных связей (или обновлений). Вот пример кода с использованием аннотации @Cascade:

import org.hibernate.annotations.Cascade;

@Entity
@Table(name = "EMPLOYEE")
public class Employee {

@OneToOne(mappedBy = "employee")
@Cascade(value = org.hibernate.annotations.CascadeType.ALL)
private Address address;

}

import org.hibernate.annotations.Cascade;

@Entity
@Table(name = "EMPLOYEE")
public class Employee {

@OneToOne(mappedBy = "employee")
@Cascade(value = org.hibernate.annotations.CascadeType.ALL)
private Address address;

}
Обратите внимание, что есть некоторые различия между enum CascadeType в Hibernate и в JPA. Поэтому обращайте внимание какой пакет вы импортируете при использовании аннотации и константы типа. Наиболее часто используемые CascadeType перечисления описаны ниже.

None: без Cascading. Формально это не тип, но если мы не указали каскадной связи, то никакая операция для родителя не будет иметь эффекта для ребенка.
ALL: Cascades save, delete, update, evict, lock, replicate, merge, persist. В общем – всё.
SAVE_UPDATE: Cascades save и update. Доступно только для hibernate.
DELETE: передает в Hibernate native DELETE действие. Только для hibernate.
DETATCH, MERGE, PERSIST, REFRESH и REMOVE – для простых операций.
LOCK: передает в Hibernate native LOCK действие.
REPLICATE: передает в Hibernate native REPLICATE действие.
### 36. Как добавить логирование log4j в Hibernate приложение?
    Добавить зависимость log4j в проект.
    Создать log4j.xml или log4j.properties файл и добавить его в classpath.
    Для веб приложений используйте ServletContextListener, а для автономных приложений DOMConfigurator или PropertyConfigurator для настройки логирования.
    Создайте экземпляр org.apache.log4j.Logger и используйте его согласно задачи.
    Может быть полезно посетить раздел Log4j2.

### 37. Как использовать JNDI DataSource сервера приложений с Hibernate Framework?
    В веб приложении лучше всего использовать контейнер сервлетов для управления пулом соединений. Поэтому лучше определить JNDI ресурс для DataSource и использовать его в веб приложении. Для этого в Hibernate нужно удалить все специфичные для базы данных свойства и использовать указания свойства JNDI DataSource:

<property name="hibernate.connection.datasource">java:comp/env/jdbc/MyLocalDB</property>
1
<property name="hibernate.connection.datasource">java:comp/env/jdbc/MyLocalDB</property>
### 38. Как интегрировать Hibernate и Spring?
    Лучше всего прочитать о настройках на сайтах фреймворков для текущей версии. Оба фреймворка поддерживают интеграцию из коробки и в общем настройка их взаимодействия не составляет труда. Общие шаги выглядят следующим образом.

Добавить зависимости для hibernate-entitymanager, hibernate-core и spring-orm.
Создать классы модели и передать реализации DAO операции над базой данных. Важно, что DAO классы используют SessionFactory, который внедряется в конфигурации бинов Spring.
Настроить конфигурационный файл Spring (смотрите в офф. документации или из примера на этом сайте).
Дополнительно появляется возможность использовать аннотацию @Transactional и перестать беспокоиться об управлении транзакцией Hibernate.
Пример использования Spring Data JPA — пример приложения Hello World. Настройки Spring Data + JPA + Hibernate + MySQL.

### 39. Что вы знаете о классе HibernateTemplate?
    Spring Framework предоставляет различные подходы для интеграции с Hibernate. Тем не менее, мы наиболее часто будем использовать подход, использующий HibernateTemplate. Есть две основные причины:

Класс скрывает детали управления сессиями и транзакциями.
Предоставляет подход основанный на шаблонах
HibernateTemplate класс скрывает трудности управления сессиями и транзакциями при использовании Hibernate для доступа к данным. Нужно только инициализировать HibernateTemplate путем передачи экземпляра SessionFactory. Spring Framework берет на себя беспокойство за детали связанные с сессиями и транзакциями. Это помогает устранить инфраструктурный код, который может вносить суматоху при увеличении сложности.
HibernateTemplate, так же как и JdbcTemplate, предоставляет шаблонный подход для доступа к данным. Когда вы используете HibernateTemplate, вы будете работать с callbacks. Обратные вызовы – это единственный механизм в шаблонном подходе, который уведомляет шаблон запускать нужную задачу. Преимущество наличия обратного вызова в том, что там только одна точка входа в слой доступа к данным. И эта точка входа определяется шаблоном, в этом случае HibernateTemplate.

В комментариях дополнили, что использование HibernateTemplate не явлется рекомендуемым. Вместо использования HibernateTemplate из пакета org.springframework.orm рекомендуется использовать декларативный подход (@Transactional). Таким образом фреймворк сам позаботится об операциях open, commit, close, flush.

Доступ к данным используя Spring Framework: Hibernate template: http://www.spring-source.ru/articles.php?type=manual&theme=articles&docs=article_08
Stackoverflow: http://stackoverflow.com/questions/18002768/why-hibernatetemplate-isnt-recommended

### 40. Как интегрировать Hibernate с Servlet или Struts2 веб приложением?
    Для интеграции необходимо использовать ServletContextListener. Более подробный пример смотрите по ссылке

http://www.journaldev.com/3557/struts2-hibernate-integration-example-tutorial
### 41. Какие паттерны применяются в Hibernate?
    Domain Model Pattern – объектная модель предметной области, включающая в себя как поведение так и данные.
    Data Mapper – слой мапперов (Mappers), который передает данные между объектами и базой данных, сохраняя их независимыми друг от друга и себя.
    Proxy Pattern – применяется для ленивой загрузки.
    Factory pattern – используется в SessionFactory
### 42. Расскажите о Hibernate Validator Framework.
    Проверка данных является неотъемлемой частью любого приложения. Hibernate Validator обеспечивает эталонную реализацию двух спецификаций JSR-303 и JSR-349 применяемых в Java. Для настройки валидации в Hibernate необходимо сделать следующие шаги.

Добавить hibernate validation зависимости в проект.
<dependency>
<groupId>javax.validation</groupId>
<artifactId>validation-api</artifactId>
<version>1.1.0.Final</version>
</dependency>
<dependency>
<groupId>org.hibernate</groupId>
<artifactId>hibernate-validator</artifactId>
<version>5.1.1.Final</version>
</dependency>

<dependency>
<groupId>javax.validation</groupId>
<artifactId>validation-api</artifactId>
<version>1.1.0.Final</version>
</dependency>
<dependency>
<groupId>org.hibernate</groupId>
<artifactId>hibernate-validator</artifactId>
<version>5.1.1.Final</version>
</dependency>
Так же требуются зависимости из JSR 341, реализующие Unified Expression Language для обработки динамических выражений и сообщений о нарушении ограничений.
<dependency>
<groupId>javax.el</groupId>
<artifactId>javax.el-api</artifactId>
<version>2.2.4</version>
</dependency>
<dependency>
<groupId>org.glassfish.web</groupId>
<artifactId>javax.el</artifactId>
<version>2.2.4</version>
</dependency>

<dependency>
<groupId>javax.el</groupId>
<artifactId>javax.el-api</artifactId>
<version>2.2.4</version>
</dependency>
<dependency>
<groupId>org.glassfish.web</groupId>
<artifactId>javax.el</artifactId>
<version>2.2.4</version>
</dependency>
Использовать необходимые аннотации в бинах.
import javax.validation.constraints.Min;
import javax.validation.constraints.NotNull;
import javax.validation.constraints.Size;

import org.hibernate.validator.constraints.CreditCardNumber;
import org.hibernate.validator.constraints.Email;

public class Employee {

    @Min(value=1, groups=EmpIdCheck.class)
    private int id;
     
    @NotNull(message="Name cannot be null")
    @Size(min=5, max=30)
    private String name;
     
    @Email
    private String email;
     
    @CreditCardNumber
    private String creditCardNumber;
....

import javax.validation.constraints.Min;
import javax.validation.constraints.NotNull;
import javax.validation.constraints.Size;

import org.hibernate.validator.constraints.CreditCardNumber;
import org.hibernate.validator.constraints.Email;

public class Employee {

    @Min(value=1, groups=EmpIdCheck.class)
    private int id;
     
    @NotNull(message="Name cannot be null")
    @Size(min=5, max=30)
    private String name;
     
    @Email
    private String email;
     
    @CreditCardNumber
    private String creditCardNumber;
....
### 43. Какие преимущества дает использование плагина Hibernate Tools Eclipse?
    Плагин Hibernate Tools упрощает настройку маппинга, конфигурационного файла. Упрощает работы с файлами свойств или xml тегами. Помогает минимизировать ошибки написания кода.

### 44. Best Practices в Hibernate.
    При использовании фреймворка Hibernate рекомендуется придерживаться некоторых правил.

Всегда проверяйте доступ к primary key. Если он создается базой данных, то вы не должны иметь сеттера.
По умолчанию hibernate устанавливает значения в поля напрямую без использования сеттеров. Если необходимо заставить хибернейт их применять, то проверьте использование аннотации @Access(value=AccessType.PROPERTY) над свойством.
Если тип доступа – property, то удостоверьтесь, что аннотация используется с геттером. Избегайте смешивания использования аннотации над обоими полями и геттером.
Используйте нативный sql запрос только там, где нельзя использовать HQL.
Используйте ordered list вместо сортированного списка из Collection API, если вам необходимо получить отсортированные данные.
Применяйте именованные запросы разумно – держите их в одном месте и используйте только для часто применяющихся запросов. Для специфичных запросов пишите их внутри конкретного бина.
В веб приложениях используйте JNDI DataSource вместо файла конфигурации для соединения с БД.
Избегайте отношений многие-ко-многим, т.к. это можно заменить двунаправленной One-to-Many и Many-to-One связью.
Для collections попробуйте использовать Lists, maps и sets. Избегайте массивов (array), т.к. они не дают преимуществ ленивой загрузки.
Не обрабатывайте исключения, которые могут откатить транзакцию и закрыть сессию. Если это проигнорировать, то Hibernate не сможет гарантировать, что состояние в памяти соответствует состоянию персистентности (могут быть коллизии данных).
Применяйте шаблон DAO для методов, которые могут использоваться в entity бинах.
Предпочитайте ленивую выборку для ассоциаций.