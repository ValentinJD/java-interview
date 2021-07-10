### 1. Расскажите о Spring Framework.
Spring Framework (или коротко Spring) — универсальный фреймворк с открытым исходным кодом для Java-платформы. Несмотря на то, что Spring Framework не обеспечивает какую-либо конкретную модель программирования, он стал широко распространённым в Java-сообществе главным образом как альтернатива и замена модели Enterprise JavaBeans. Spring Framework предоставляет бо́льшую свободу Java-разработчикам в проектировании; кроме того, он предоставляет хорошо документированные и лёгкие в использовании средства решения проблем, возникающих при создании приложений корпоративного масштаба. Обычно Spring описывают как облегченную платформу для построения Java-приложений, но с этим утверждением связаны два интересных момента. Во-первых, Spring можно использовать для построения любого приложения на языке Java (т.е. автономных, веб приложений, приложений JEE и т.д.), что отличает Spring от многих других платформ, таких как Apache Struts, которая ограничена только веб-приложениями. Во-вторых, характеристика “облегченная” в действительности не имеет никакого отношения к количеству классов или размеру дистрибутива; напротив, она определяет принцип всей философии Spring — минимальное воздействие. Платформа Spring является облегченной в том смысле, что для использования ядра Spring вы должны вносить минимальные (если вообще какие-либо) изменения в код своего приложения, а если в какой-то момент вы решите больше не пользоваться Spring, то и это сделать очень просто. Обратите внимание, что речь идет только о ядре Spring — многие дополнительные компоненты Spring, такие как доступ к
данным, требуют более тесной привязки к Spring Framework.

### 2. Какие некоторые из важных особенностей и преимуществ Spring Framework?
Spring Framework обеспечивает решения многих задач, с которыми сталкиваются Java-разработчики и организации, которые хотят создать информационную систему, основанную на платформе Java. Из-за широкой функциональности трудно определить наиболее значимые структурные элементы, из которых он состоит. Spring Framework не всецело связан с платформой Java Enterprise, несмотря на его масштабную интеграцию с ней, что является важной причиной его популярности.

Spring Framework, вероятно, наиболее известен как источник расширений (features), нужных для эффективной разработки сложных бизнес-приложений вне тяжеловесных программных моделей, которые исторически были доминирующими в промышленности. Ещё одно его достоинство в том, что он ввел ранее неиспользуемые функциональные возможности в сегодняшние господствующие методы разработки, даже вне платформы Java. Этот фреймворк предлагает последовательную модель и делает её применимой к большинству типов приложений, которые уже созданы на основе платформы Java. Считается, что Spring Framework реализует модель разработки, основанную на лучших стандартах индустрии, и делает её доступной во многих областях Java. Таким образом к достоинствам Spring можно отнести:

Относительная легкость в изучении и применении фреймворка в разработке и поддержке приложения.
Внедрение зависимостей (DI) и инверсия управления (IoC) позволяют писать независимые друг от друга компоненты, что дает преимущества в командной разработке, переносимости модулей и т.д..
Spring IoC контейнер управляет жизненным циклом Spring Bean и настраивается наподобие JNDI lookup (поиска).
Проект Spring содержит в себе множество подпроектов, которые затрагивают важные части создания софта, такие как вебсервисы, веб программирование, работа с базами данных, загрузка файлов, обработка ошибок и многое другое. Всё это настраивается в едином формате и упрощает поддержку приложения.
### 3. Что вы понимаете под Dependency Injection (DI)?
Внедрение зависимости (Dependency injection, DI) — процесс предоставления внешней зависимости программному компоненту. Является специфичной формой «инверсии управления» ( Inversion of control, IoC), когда она применяется к управлению зависимостями. В полном соответствии с принципом единой обязанности объект отдаёт заботу о построении требуемых ему зависимостей внешнему, специально предназначенному для этого общему механизму. К достоинствам применения DI можно отнести:

Сокращение объема связующего кода. Одним из самых больших плюсов DI является возможность значительного сокращения объема кода, который должен быть написан для связывания вместе различных компонентов приложения. Зачастую этот код очень прост — при создании зависимости должен создаваться новый экземпляр соответствующего объекта.
Упрощенная конфигурация приложения. За счет применения DI процесс конфигурирования приложения значительно упрощается. Для конфигурирования классов, которые могут быть внедрены в другие классы, можно использовать аннотации или XML-файлы.
Возможность управления общими зависимостями в единственном репозитории. При традиционном подходе к управлению зависимостями в общих службах, к которым относятся, например, подключение к источнику данных, транзакция, удаленные службы и т.п., вы создаете экземпляры (или получаете их из определенных фабричных классов) зависимостей там, где они нужны — внутри зависимого класса. Это приводит к распространению зависимостей по множеству классов в приложении, что может затруднить их изменение. В случае использования DI вся информация об общих зависимостях содержится в единственном репозитории (в Spring есть возможность хранить эту информацию в XML-файлах или Java классах), что существенно упрощает управление зависимостями и снижает количество возможных ошибок.
Улучшенная возможность тестирования. Когда классы проектируются для DI, становится возможной простая замена зависимостей. Это особенно полезно при тестировании приложения.
Стимулирование качественных проектных решений для приложений. Вообще говоря, проектирование для DI означает проектирование с использованием интерфейсов. Используя Spring, вы получаете в свое распоряжение целый ряд средств DI и можете сосредоточиться на построении логики приложения, а не на поддерживающей DI платформе.
### 4. Как реализуется DI в Spring Framework?
Реализация DI в Spring основана на двух ключевых концепциях Java — компонентах JavaBean и интерфейсах. При использовании Spring в качестве поставщика DI вы получаете гибкость определения конфигурации зависимостей внутри своих приложений разнообразными путями (т.е. внешне в XML-файлах, с помощью конфигурационных Java классов Spring или посредством аннотаций Java в коде). Компоненты JavaBean (также называемые POJO (Plain Old Java Object — простой старый объект Java)) предоставляют стандартный механизм для создания ресурсов Java, которые являются конфигурируемыми множеством способов. За счет применения DI объем кода, который необходим при проектировании приложения на основе интерфейсов, снижается почти до нуля. Кроме того, с помощью интерфейсов можно получить максимальную отдачу от DI, потому что бины могут использовать любую реализацию интерфейса для удовлетворения их зависимости.

К типам реализации внедрения зависимостей в Spring относят:

Constructor Dependency Injection — это тип внедрения зависимостей, при котором зависимости компонента предоставляются ему в его конструкторе (или конструкторах).

public class ConstructorInjection {

private Dependency dependency;
  
  public ConstructorInjection(Dependency dependency) {
         this.dependency = dependency;
  }
}

public class ConstructorInjection {
 
private Dependency dependency;
  
  public ConstructorInjection(Dependency dependency) {
         this.dependency = dependency;
  }
}
Setter Dependency Injection – контейнер IoC внедряет зависимости компонента в компонент через методы установки в стиле JavaBean.

public class SetterInjection {
private Dependency dependency;
   public void setDependency(Dependency dependency) {
           this.dependency = dependency;
   }
}

public class SetterInjection {
private Dependency dependency;
   public void setDependency(Dependency dependency) {
           this.dependency = dependency;
   }
}
### 5. Какие преимущества использования Spring Tool Suite?
Для упрощения процесса разработки основанных на Spring приложений в Eclipse (наиболее часто используемая бесплатная IDE-среда для разработки Java-приложений), в рамках Spring создан проект Spring IDE. Проект бесплатный. Он интегрирован в Eclipse IDE, Spring IDE, Mylyn (среда разработки в Eclipse, основанная на задачах), Maven for Eclipse, AspectJ Development Tool.

### 6. Приведите названия некоторых важных Spring модулей.
+ Inversion of Control-контейнер: конфигурирование компонентов приложений и управление жизненным циклом Java-объектов.
+ Фреймворк аспектно-ориентированного программирования: работает с функциональностью, которая не может быть реализована возможностями объектно-ориентированного программирования на Java без потерь.
+ Фреймворк доступа к данным: работает с системами управления реляционными базами данных на Java-платформе, используя JDBC- и ORM-средства и обеспечивая решения задач, которые повторяются в большом числе Java-based environments.
+ Фреймворк управления транзакциями: координация различных API управления транзакциями и инструментарий настраиваемого управления транзакциями для объектов Java.
+ Фреймворк MVC: каркас, основанный на HTTP и сервлетах, предоставляющий множество возможностей для расширения и настройки (customization).
+ Фреймворк удалённого доступа: конфигурируемая передача Java-объектов через сеть в стиле RPC, поддерживающая RMI, CORBA,HTTP-based протоколы, включая web-сервисы (SOAP).
+ Фреймворк аутентификации и авторизации: конфигурируемый инструментарий процессов аутентификации и авторизации, поддерживающий много популярных и ставших индустриальными стандартами протоколов, инструментов, практик через дочерний проект Spring Security (ранее известный как Acegi).
+ Фреймворк удалённого управления: конфигурируемое представление и управление Java-объектами для локальной или удалённой конфигурации с помощью JMX.
+ Фреймворк работы с сообщениями: конфигурируемая регистрация объектов-слушателей сообщений для прозрачной обработки сообщений из очереди сообщений с помощью JMS, улучшенная отправка сообщений по стандарту JMS API.
Тестирование: каркас, поддерживающий классы для написания модульных и интеграционных тестов.
### 7. Что вы понимаете под аспектно-ориентированным программированием (Aspect Oriented Programming — AOP)?
Аспектно-ориентированное программирование (АОП) — это одна из “моделей программирования текущего момента” в мире Java. АОП предоставляет возможность реализации сквозной логики — т.е. логики, которая применяется к множеству частей приложения — в одном месте и обеспечения автоматического применения этой логики по всему приложению. Подход Spring к АОП заключается в создании “динамических прокси” для целевых объектов и “привязывании” объектов к конфигурированному совету для выполнения сквозной логики.

### 8. Что такое Aspect, Advice, Pointcut, JoinPoint и Advice Arguments в АОП?
Точки соединения. 
+ Точка соединения (joinpoint) — это четко определенная точка во время выполнения приложения. Типовые примеры точек соединения включают обращение к методу, собственно Method Invocation, инициализацию класса и создание экземпляра объекта. Точки соединения являются ключевой концепцией АОП и определяют места в приложении, в которые можно вставлять дополнительную логику с использованием АОП.
+ Советы (advice). Фрагмент кода, который должен выполняться в отдельной точке соединения, представляет собой совет (advice). Существует несколько типов советов, среди которых перед, когда совет выполняется до точки соединения, и после, когда совет выполняется после точки соединения. В ООП совет принимает форму метода внутри класса.
+ Срезы. Срез (pointcut) — это коллекция точек соединения, которая используется для определения ситуации, когда совет должен быть выполнен. Создавая срезы, вы получаете точный контроль над тем, как применять совет к компонентам приложения. Как упоминалось ранее, типичной точкой соединения является Method Invocation. А типичный срез представляет собой коллекцию всех точек соединения Method Invocation в отдельном классе. Часто между срезами можно установить сложные отношения, чтобы обеспечить дополнительные ограничения на то, когда будет выполнен совет.
+ Аспекты. Аспект (aspect) — это комбинация совета и срезов. Такая комбинация дает в результате определение логики, которая должна быть включена в приложение, и указание мест, где она должна выполняться.
+ Связывание. Связывание (weaving) представляет собой процесс действительной вставки аспектов в определенную точку кода приложения. Для решений АОП времени компиляции это делается на этапе компиляции, обычно в виде дополнительного шага процесса сборки. Аналогично, для решений АОП времени выполнения связывание происходит динамически во время выполнения. В AspectJ поддерживается еще один механизм связывания под названием связывание во время загрузки (load-time weaving — LTW), который перехватывает лежащий в основе загрузчик классов JVM и обеспечивает связывание с байт-кодом, когда он загружается загрузчиком классов.
+ Цель. Цель (target) — это объект, поток выполнения которого изменяется каким-то процессом АОП. На целевой объект часто ссылаются как на объект, снабженный советом.
+ Введение. Введение (introduction) представляет собой процесс, посредством которого можно изменить структуру объекта за счет введения в него дополнительных методов или полей. Введение можно использовать для обеспечения реализации любым объектом определенного интерфейса без необходимости в том, чтобы класс этого объекта реализовывал такой интерфейс явно.
### 9. В чем разница между Spring AOP и AspectJ АОП?
AspectJ де-факто является стандартом реализации АОП. Реализация АОП от Spring имеет некоторые отличия:

Spring AOP немного проще, т.к. нет необходимости следить за процессом связывания.
Spring AOP поддерживает аннотации AspectJ, таким образом мы можем работать в спринг проекте похожим образом с AspectJ проектом.
Spring AOP поддерживает только proxy-based АОП и может использовать только один тип точек соединения – Method Invocation. AspectJ поддерживает все виды точек соединения.
Недостатком Spring AOP является работа только со своими бинами, которые существуют в Spring Context.
### 10. Что такое IoC контейнер Spring?
По своей сути IoC, а, следовательно, и DI, направлены на то, чтобы предложить простой механизм для предоставления зависимостей компонента (часто называемых коллабораторами объекта) и управления этими зависимостями на протяжении всего их жизненного цикла. Компонент, который требует определенных зависимостей, зачастую называют зависимым объектом или, в случае IoC, целевым объектом. Вполне уместно сейчас заявить, что IoC предоставляет службы, через которые компоненты могут получать доступ к своим зависимостям, и службы для взаимодействия с зависимостями в течение их времени жизни. В общем случае IoC может быть расщеплена на два подтипа: инверсия управления (Dependency Injection) и поиск зависимости (Dependency Lookup). Инверсия управления — это крупная часть того, делает Spring, и ядро реализации Spring основано на инверсии управления, хотя также предоставляются и средства Dependency Lookup. Когда платформа Spring предоставляет коллабораторы зависимому объекту автоматически, она делает это с использованием инверсии управления (Dependency Injection). В приложении, основанном на Spring, всегда предпочтительнее применять Dependency Injection для передачи коллабораторов зависимым объектам вместо того, чтобы заставлять зависимые объекты получать коллабораторы через поиск.

### 11. Что такое Spring бин?
Термин бин в Spring используется для ссылки на любой компонент, управляемый контейнером. Обычно бины на определенном уровне придерживаются спецификации JavaBean, но это не обязательно особенно если для связывания бинов друг с другом планируется применять Constructor Injection. Для получения экземпляра бина используется ApplicationContext. IoC контейнер управляет жизненным циклом спринг бина, областью видимости и внедрением.

### 12. Какое значение имеет конфигурационный файл Spring Bean?
Конфигурационный файл спринг определяет все бины, которые будут инициализированы в Spring Context. При создании экземпляра Spring ApplicationContext будет прочитан конфигурационный xml файл и выполнены указанные в нем необходимые инициализации. Отдельно от базовой конфигурации, в файле могут содержаться описание перехватчиков (interceptors), view resolvers, настройки локализации и др..

### 13. Какие различные способы настроить класс как Spring Bean?
Существует несколько способов работы с классами в Spring:

XML конфигурация:

<bean name="myBean" class="ru.javastudy.spring.beans.MyBean"></bean>
1
<bean name="myBean" class="ru.javastudy.spring.beans.MyBean"></bean>
Java based конфигурация. Все настройки и указания бинов прописываются в java коде:

@Configuration
@ComponentScan(value="ru.javastudy.spring.main")
public class MyConfiguration {
 
    @Bean
    public MyService getService(){
        return new MyService();
    }
}

@Configuration
@ComponentScan(value="ru.javastudy.spring.main")
public class MyConfiguration {
 
    @Bean
    public MyService getService(){
        return new MyService();
    }
}
Для извлечения бина из контекста используется следующий подход:

AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
        MyConfiguration.class);
MyService service = ctx.getBean(MyService.class);

AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(
        MyConfiguration.class);
MyService service = ctx.getBean(MyService.class);
Annotation based конфигурация. Можно использовать внутри кода аннотации @Component, @Service, @Repository, @Controller для указания классов в качестве спринг бинов. Для их поиска и управления контейнером прописывается настройка в xml файле:

<context:component-scan base-package="ru.javastudy.spring" />
1
<context:component-scan base-package="ru.javastudy.spring" />
### 14. Какие вы знаете различные scope у Spring Bean?
В Spring предусмотрены различные области времени действия бинов:

singleton – может быть создан только один экземпляр бина. Этот тип используется спрингом по умолчанию, если не указано другое. Следует осторожно использовать публичные свойства класса, т.к. они не будут потокобезопасными.
prototype – создается новый экземпляр при каждом запросе.
request –  аналогичен prototype, но название служит пояснением к использованию бина в веб приложении. Создается новый экземпляр при каждом HTTP request.
session – новый бин создается в контейнере при каждой новой HTTP сессии.
global-session: используется для создания глобальных бинов на уровне сессии для Portlet  приложений.
### 15. Что такое жизненный цикл Spring Bean?
Жизненный цикл Spring бина – время существования класса. Spring бины инициализируются при инициализации Spring контейнера и происходит внедрение всех зависимостей. Когда контейнер уничтожается, то уничтожается и всё содержимое. Если нам необходимо задать какое-либо действие при инициализации и уничтожении бина, то нужно воспользоваться методами init() и destroy(). Для этого можно использовать аннотации @PostConstruct и @PreDestroy().

 @PostConstruct
    public void init(){
        System.out.println("Bean init method called");
    }
     

    @PreDestroy
    public void destroy(){
        System.out.println("Bean destroy method called");
    }

 @PostConstruct
    public void init(){
        System.out.println("Bean init method called");
    }
     
 
    @PreDestroy
    public void destroy(){
        System.out.println("Bean destroy method called");
    }
Или через xml конфигурацию:

<bean name="myBean" class="ru.javastudy.spring.MyBean"
        init-method="init" destroy-method="destroy">
    <property name="someProp" ref="someProp"></property>
</bean>

<bean name="myBean" class="ru.javastudy.spring.MyBean"
        init-method="init" destroy-method="destroy">
    <property name="someProp" ref="someProp"></property>
</bean>
### 16. Как получить объекты ServletContext и ServletConfig внутри Spring Bean?
Доступны два способа для получения основных объектов контейнера внутри бина:

Реализовать один из Spring*Aware (ApplicationContextAware, ServletContextAware, ServletConfigAware и др.) интерфейсов.
Использовать автоматическое связывание @Autowired в спринг. Способ работает внутри контейнера спринг.
@Autowired
ServletContext servletContext;
1
2
@Autowired
ServletContext servletContext;
### 17. Что такое связывание в Spring и расскажите об аннотации @Autowired?
Процесс внедрения зависимостей в бины при инициализации называется Spring Bean Wiring. Считается хорошей практикой задавать явные связи между зависимостями, но в Spring предусмотрен дополнительный механизм связывания @Autowired. Аннотация может использоваться над полем или методом для связывания по типу. Чтобы аннотация заработала, необходимо указать небольшие настройки в конфигурационном файле спринг с помощью элемента context:annotation-config.

### 18. Какие различные типы автоматического связывания в Spring?
Существует четыре вида связывания в спринг:

autowire byName,
autowire byType,
autowire by constructor,
autowiring by @Autowired and @Qualifier annotations
### 19. Является ли Spring бин потокобезопасным?
По умолчанию бин задается как синглтон в Spring. Таким образом все публичные  переменные класса могут быть изменены одновременно из разных мест. Так что – нет, не является. Однако поменяв область действия бина на request, prototype, session он станет потокобезопасным, но это скажется на производительности.

### 20. Что такое контроллер в Spring MVC?
Ключевым интерфейсом в Spring MVC является Controller. Контроллер обрабатывает запросы к действиям, осуществляемые пользователями в пользовательском интерфейсе, взаимодействуя с уровнем обслуживания, обновляя модель и направляя пользователей на соответствующие представления в зависимости от результатов выполнения. Controller — управление, связь между моделью и видом.

Dispatcher-servlet-diagram

Основным контроллером в Spring MVC является org.springframework.web.servlet.DispatcherServlet. Задается аннотацией @Controller и часто используется с аннотацией @RequestMapping, которая указывает какие запросы будут обрабатываться этим контроллером.

Читайте так же – Spring MVC — основные понятия, архитектура.

### 21. Какая разница между аннотациями @Component, @Repository и @Service в Spring?
@Component используется для указания класса в качестве компонента спринг. При использовании поиска аннотаций, такой класс будет сконфигурирован как spring bean.

@Controller специальный тип класса, применяемый в MVC приложениях. Обрабатывает запросы и часто используется с аннотацией @RequestMapping.

@Repository указывает, что класс используется для работы с поиском, получением и хранением данных. Аннотация может использоваться для реализации шаблона DAO.

@Service указывает, что класс является сервисом для реализации бизнес логики (на самом деле не отличается от Component, но просто помогает разработчику указать смысловую нагрузку класса).

Для указания контейнеру на класс-бин можно использовать любую из этих аннотаций. Но различные имена позволяют различать назначение того или иного класса.
### 22. Расскажите, что вы знаете о DispatcherServlet и ContextLoaderListener.
DispatcherServlet – сервлет диспетчера. Этот сервлет анализирует запросы и направляет их соответствующему контроллеру для обработки. В Spring MVC класс DispatcherServlet является центральным сервлетом, который получает запросы и направляет их соответствующим контроллерам. В приложении Spring MVC может существовать произвольное количество экземпляров DispatcherServlet, предназначенных для разных целей (например, для обработки запросов пользовательского интерфейса, запросов веб-служб REST и т.д.). Каждый экземпляр DispatcherServlet имеет собственную конфигурацию WebApplicationContext, которая определяет характеристики уровня сервлета, такие как контроллеры, поддерживающие сервлет, отображение обработчиков, распознавание представлений, интернационализация, оформление темами, проверка достоверности, преобразование типов и форматирование и т.п.

ContextLoaderListener – слушатель при старте и завершении корневого класса Spring WebApplicationContext. Основным назначением является связывание жизненного цикла ApplicationContext и ServletContext, а так же автоматического создания ApplicationContext. Можно использовать этот класс для доступа к бинам из различных контекстов спринг. Настраивается в web.xml:

<context-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>/WEB-INF/spring/root-context.xml</param-value>
</context-param>
 
<listener>
    <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
</listener>

<context-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>/WEB-INF/spring/root-context.xml</param-value>
</context-param>
 
<listener>
    <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
</listener>

### 23. Что такое ViewResolver в Spring?
ViewResolver – распознаватель представлений. Интерфейс ViewResolver в Spring MVC (из пакета org.springframework.web.servlet) поддерживает распознавание представлений на основе логического имени, возвращаемого контроллером. Для поддержки различных механизмов распознавания представлений предусмотрено множество классов реализации. Например, класс UrlBasedViewResolver поддерживает прямое преобразование логических имен в URL. Класс ContentNegotiatingViewResolver поддерживает динамическое распознавание представлений в зависимости от типа медиа, поддерживаемого клиентом (XML, PDF, JSON и т.д.). Существует также несколько реализаций для интеграции с различными технологиями представлений, такими как FreeMarker (FreeMarkerViewResolver), Velocity (VelocityViewResolver) и JasperReports (JasperReportsViewResolver).

<!-- Resolves views selected for rendering by @Controllers to .jsp resources
           in the /WEB-INF/views directory -->
       <bean
               class="org.springframework.web.servlet.view.InternalResourceViewResolver">
              <property name="prefix" value="/WEB-INF/views/" />
              <property name="suffix" value=".jsp" />
       </bean>


InternalResourceViewResolver – реализация ViewResolver, которая позволяет находить представления, которые возвращает контроллер для последующего перехода к нему. Ищет по заданному пути, префиксу, суффиксу и имени.

Дополнительная информация – Spring MVC — описание интерфейса ViewResolver.

### 24. Что такое MultipartResolver и когда его использовать?
Интерфейс MultipartResolver используется для загрузки файлов. Существуют две реализации: CommonsMultipartResolver и StandardServletMultipartResolver, которые позволяют фреймворку загружать файлы. По умолчанию этот интерфейс не включается в приложении и необходимо указывать его в файле конфигурации. После настройки любой запрос о загрузке будет отправляться этому интерфейсу.

 <beans:bean id="multipartResolver" class="org.springframework.web.multipart.commons.CommonsMultipartResolver">
 
  <!-- setting maximum upload size -->
        <beans:property name="maxUploadSize" value="100000" />
 
  </beans:bean>

Пример – Spring MVC — загрузка файла

### 25. Как обрабатывать исключения в Spring MVC Framework?
В Spring MVC интерфейс HandlerExceptionResolver (из пакета org.springframework.web.servlet) предназначен для работы с непредвиденными исключениями, возникающими во время выполнения обработчиков. По умолчанию DispatcherServlet регистрирует класс DefaultHandlerExceptionResolver (из пакета org.springframework.web.servlet.mvc.support). Этот распознаватель обрабатывает определенные стандартные исключения Spring MVC, устанавливая специальный код состояния ответа. Можно также реализовать собственный обработчик исключений, аннотировав метод контроллера с помощью аннотации @ExceptionHandler и передав ей в качестве атрибута тип исключения. В общем случае обработку исключений можно описать таким образом:

Controller Based – указать методы для обработки исключения в классе контроллера. Для этого нужно пометить такие методы аннотацией @ExceptionHandler.

Global Exception Handler – для обработки глобальных исключений спринг предоставляет аннотацию @ControllerAdvice.

HandlerExceptionResolver implementation – Spring Framework предоставляет интерфейс HandlerExceptionResolver, который позволяет задать глобального обработчика исключений. Реализацию этого интерфейса можно использовать для создания собственных глобальных обработчиков исключений в приложении.

### 26. Как создать ApplicationContext в программе Java?
В независимой Java программе ApplicationContext можно создать следующим образом:

AnnotationConfigApplicationContext: при использовании Spring в качестве автономного приложения можно создать, инициализировать контейнер с помощью аннотаций.
ClassPathXmlApplicationContext: второй подход использует xml файл, в котором задаются необходимые настройки, а затем используем класс для загрузки файла и получения объекта контейнера.
FileSystemXmlApplicationContext: аналогичен варианту с xml, но с возможностью загрузки файла конфигурации из любого места файловой системы.
### 27. Можем ли мы иметь несколько файлов конфигурации Spring?
С помощью указания contextConfigLocation можно задать несколько файлов конфигурации Spring. Параметры указываются через запятую или пробел:

<servlet>
    <servlet-name>appServlet</servlet-name>
    <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    <init-param>
        <param-name>contextConfigLocation</param-name>
        <param-value>/WEB-INF/spring/appServlet/servlet-context.xml,/WEB-INF/spring/appServlet/servlet-jdbc.xml</param-value>
    </init-param>
    <load-on-startup>1</load-on-startup>
</servlet>

<servlet>
    <servlet-name>appServlet</servlet-name>
    <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    <init-param>
        <param-name>contextConfigLocation</param-name>
        <param-value>/WEB-INF/spring/appServlet/servlet-context.xml,/WEB-INF/spring/appServlet/servlet-jdbc.xml</param-value>
    </init-param>
    <load-on-startup>1</load-on-startup>
</servlet>
Поддерживается возможность указания нескольких корневых файлов конфигурации Spring:

<context-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>/WEB-INF/spring/root-context.xml /WEB-INF/spring/root-security.xml</param-value>
</context-param>

<context-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>/WEB-INF/spring/root-context.xml /WEB-INF/spring/root-security.xml</param-value>
</context-param>
Файл конфигурации можно импортировать:

<beans:import resource="spring-jdbc.xml"/>
1
<beans:import resource="spring-jdbc.xml"/>
### 28. Какие минимальные настройки, чтобы создать приложение Spring MVC?
Для создания простого Spring MVC приложения необходимо пройти следующие шаги:

Добавить зависимости spring-context и spring-webmvc в проект.
Указать DispatcherServlet в web.xml для обработки запросов внутри приложения.
Задать определение spring bean (аннотацией или в xml). Добавить определение view resolver для представлений.
Настроить класс контроллер для обработки клиентских запросов.
Смотрите пример Spring MVC — Hello World, пример приложения.

### 29. Как бы вы связали Spring MVC Framework и архитектуру MVC?
Моделью (Model) выступает любой Java bean в Spring. Внутри класса могут быть заданы различные атрибуты и свойства для использования в представлении.
Преставление (View) – JSP страница, HTML файл и т.п. служат для отображения необходимой информации пользователю. Представление передает обработку запросов к диспетчеру сервлетов (контроллеру).
DispatcherServlet (Controller) – это главный контроллер в приложении Spring MVC, который обрабатывает все входящие запросы и передает их для обработки в различные методы в контроллеры.
### 30. Как добиться локализации в приложениях Spring MVC?
Spring MVC предоставляет очень простую и удобную возможность локализации приложения. Для этого необходимо сделать следующее:

Создать файл resource bundle, в котором будут заданы различные варианты локализированной информации.
Определить messageSource в конфигурации Spring используя классы ResourceBundleMessageSource или ReloadableResourceBundleMessageSource.
Определить localeResolver класса CookieLocaleResolver для включения возможности переключения локали.
С помощью элемента spring:message DispatcherServlet будет определять в каком месте необходимо подставлять локализированное сообщение в ответе.
<beans:bean id="messageSource"
    class="org.springframework.context.support.ReloadableResourceBundleMessageSource">
    <beans:property name="basename" value="classpath:messages" />
    <beans:property name="defaultEncoding" value="UTF-8" />
</beans:bean>
 
<beans:bean id="localeResolver"
    class="org.springframework.web.servlet.i18n.CookieLocaleResolver">
    <beans:property name="defaultLocale" value="en" />
    <beans:property name="cookieName" value="myAppLocaleCookie"></beans:property>
    <beans:property name="cookieMaxAge" value="3600"></beans:property>
</beans:bean>
 
<interceptors>
    <beans:bean
        class="org.springframework.web.servlet.i18n.LocaleChangeInterceptor">
        <beans:property name="paramName" value="locale" />
    </beans:bean>
</interceptors>

<beans:bean id="messageSource"
    class="org.springframework.context.support.ReloadableResourceBundleMessageSource">
    <beans:property name="basename" value="classpath:messages" />
    <beans:property name="defaultEncoding" value="UTF-8" />
</beans:bean>
 
<beans:bean id="localeResolver"
    class="org.springframework.web.servlet.i18n.CookieLocaleResolver">
    <beans:property name="defaultLocale" value="en" />
    <beans:property name="cookieName" value="myAppLocaleCookie"></beans:property>
    <beans:property name="cookieMaxAge" value="3600"></beans:property>
</beans:bean>
 
<interceptors>
    <beans:bean
        class="org.springframework.web.servlet.i18n.LocaleChangeInterceptor">
        <beans:property name="paramName" value="locale" />
    </beans:bean>
</interceptors>
### 31. Как мы можем использовать Spring для создания веб-службы RESTful, возвращающей JSON?
Spring Framework позволяет создавать Restful веб сервисы и возвращать данные в формате JSON. Spring обеспечивает интеграцию с Jackson JSON API для возможности отправки JSON ответов в restful web сервисе. Для отправки ответа в формате JSON из Spring MVC приложения необходимо произвести следующие настройки:

Добавить зависимости Jackson JSON. С помощью maven это делается так:
<!-- Jackson -->
<dependency>
    <groupId>com.fasterxml.jackson.core</groupId>
    <artifactId>jackson-databind</artifactId>
    <version>${jackson.databind-version}</version>
</dependency>

<!-- Jackson -->
<dependency>
    <groupId>com.fasterxml.jackson.core</groupId>
    <artifactId>jackson-databind</artifactId>
    <version>${jackson.databind-version}</version>
</dependency>
Настроить бин RequestMappingHandlerAdapter в файле конфигурации Spring и задать свойство messageConverters на использование бина MappingJackson2HttpMessageConverter.
<!-- Configure to plugin JSON as request and response in method handler -->
<beans:bean class="org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter">
    <beans:property name="messageConverters">
        <beans:list>
            <beans:ref bean="jsonMessageConverter"/>
        </beans:list>
    </beans:property>
</beans:bean>
  
<!-- Configure bean to convert JSON to POJO and vice versa -->
<beans:bean id="jsonMessageConverter" class="org.springframework.http.converter.json.MappingJackson2HttpMessageConverter">
</beans:bean>

<!-- Configure to plugin JSON as request and response in method handler -->
<beans:bean class="org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter">
    <beans:property name="messageConverters">
        <beans:list>
            <beans:ref bean="jsonMessageConverter"/>
        </beans:list>
    </beans:property>
</beans:bean>
  
<!-- Configure bean to convert JSON to POJO and vice versa -->
<beans:bean id="jsonMessageConverter" class="org.springframework.http.converter.json.MappingJackson2HttpMessageConverter">
</beans:bean>
В контроллере указать с помощью аннотации @ResponseBody возвращение Object:
@RequestMapping(value = EmpRestURIConstants.GET_EMP, method = RequestMethod.GET)
public @ResponseBody Employee getEmployee(@PathVariable("id") int empId) {
    logger.info("Start getEmployee. ID="+empId);
      
    return empData.get(empId);
}

@RequestMapping(value = EmpRestURIConstants.GET_EMP, method = RequestMethod.GET)
public @ResponseBody Employee getEmployee(@PathVariable("id") int empId) {
    logger.info("Start getEmployee. ID="+empId);
      
    return empData.get(empId);
}
### 32. Приведите пример часто используемых аннотаций Spring.
@Controller – класс фронт контроллера в проекте Spring MVC.
@RequestMapping – позволяет задать шаблон маппинга URI в методе обработчике контроллера.
@ResponseBody – позволяет отправлять Object в ответе. Обычно используется для отправки данных формата XML или JSON.
@PathVariable – задает динамический маппинг значений из URI внутри аргументов метода обработчика.
@Autowired – используется для автоматического связывания зависимостей в spring beans.
@Qualifier – используется совместно с @Autowired для уточнения данных связывания, когда возможны коллизии (например одинаковых имен\типов).
@Service – указывает что класс осуществляет сервисные функции.
@Scope – указывает scope у spring bean.
@Configuration, @ComponentScan и @Bean – для java based configurations.
AspectJ аннотации для настройки aspects и advices, @Aspect, @Before, @After,@Around, @Pointcut и др.
### 33. Можем ли мы послать объект как ответ метода обработчика контроллера?
Да, это возможно. Для этого используется аннотация @ResponseBody. Так можно отправлять ответы в виде JSON, XML в restful веб сервисах.

### 34. Как загрузить файл в Spring MVC?
Внутри спринг предусмотрен интерфейс MultipartResolver для обеспечения загрузки файлов. Фактически нужно настроить файл конфигурации для указания обработчика загрузки файлов, а затем задать необходимый метод в контроллере spring.

Смотрите пример – Spring MVC — загрузка файла или Spring MVC — загрузка файла с валидацией.

### 35. Как проверить (валидировать) данные формы в Spring Web MVC Framework?
Spring поддерживает аннотации валидации из JSR-303, а так же возможность создания своих реализаций классов валидаторов. Пример использования аннотаций:

    @Size(min=2, max=30) 
    private String name;
      
    @NotEmpty @Email
    private String email;
      
    @NotNull @Min(18) @Max(100)
    private Integer age;
      
    @NotNull
    private Gender gender;
      
    @DateTimeFormat(pattern="MM/dd/yyyy")
    @NotNull @Past
    private Date birthday;

    @Size(min=2, max=30) 
    private String name;
      
    @NotEmpty @Email
    private String email;
      
    @NotNull @Min(18) @Max(100)
    private Integer age;
      
    @NotNull
    private Gender gender;
      
    @DateTimeFormat(pattern="MM/dd/yyyy")
    @NotNull @Past
    private Date birthday;
### 36. Что вы знаете о Spring MVC Interceptor и как он используется?
Перехватчики в Spring (Spring Interceptor) являются аналогом Servlet Filter и позволяют перехватывать запросы клиента и обрабатывать их. Перехватить запрос клиента можно в трех местах: preHandle, postHandle и afterCompletion.

preHandle – метод используется для обработки запросов, которые еще не были переданы в метода обработчик контроллера. Должен вернуть true для передачи следующему перехватчику или в handler method. False укажет на обработку запроса самим обработчиком и отсутствию необходимости передавать его дальше. Метод имеет возможность выкидывать исключения и пересылать ошибки к представлению.
postHandle – вызывается после handler method, но до обработки DispatcherServlet для передачи представлению. Может использоваться для добавления параметров в объект ModelAndView.
afterCompletion – вызывается после отрисовки представления.
Для создания обработчика необходимо расширить абстрактный класс HandlerInterceptorAdapter или реализовать интерфейс HandlerInterceptor. Так же нужно указать перехватчики в конфигурационном файле Spring.

<!-- Configuring interceptors based on URI -->
    <interceptors>
        <interceptor>
            <mapping path="/home" />
            <beans:bean class="ru.javastudy.spring.RequestProcessingTimeInterceptor"></beans:bean>
        </interceptor>
    </interceptors>

<!-- Configuring interceptors based on URI -->
    <interceptors>
        <interceptor>
            <mapping path="/home" />
            <beans:bean class="ru.javastudy.spring.RequestProcessingTimeInterceptor"></beans:bean>
        </interceptor>
    </interceptors>
### 37. Spring JdbcTemplate класс и его применение.
Spring предоставляет отличную поддержку JDBC API и предлагает класс утилиту JdbcTemplate, с помощью которого можно избавиться от многократного повторения похожего кода в приложении (вроде операций open \ closing connection; ResultSet, PreparedStatement и др.). Для подключения необходимо настроить файл конфигурации spring и получить объект JdbcTemplate. Например.

spring.xml:

<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">
 
    <bean id="employeeDAO" class="com.journaldev.spring.jdbc.dao.EmployeeDAOImpl">
        <property name="dataSource" ref="dataSource" />
    </bean>
     
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
 
        <property name="driverClassName" value="com.mysql.jdbc.Driver" />
        <property name="url" value="jdbc:mysql://localhost:3306/TestDB" />
        <property name="username" value="pankaj" />
        <property name="password" value="pankaj123" />
    </bean>
 
</beans>

Пример использования JdbcTemplate:


 @Override
    public void save(Employee employee) {
        String query = "insert into Employee (id, name, role) values (?,?,?)";
         
        JdbcTemplate jdbcTemplate = new JdbcTemplate(dataSource);
         
        Object[] args = new Object[] {employee.getId(), employee.getName(), employee.getRole()};
         
        int out = jdbcTemplate.update(query, args);
         
        if(out !=0){
            System.out.println("Employee saved with id="+employee.getId());
        }else System.out.println("Employee save failed with id="+employee.getId());
    }

### 38. Как использовать Tomcat JNDI DataSource в веб-приложении Spring?
Для использования контейнера сервлетов настроенного на использование JNDI DataSource, необходимо задать соответствующее свойство в файле конфигурации и затем внедрять его как зависимость. Далее мы можем использовать объект JdbcTemplate для выполнения операций с базами данных.

<beans:bean id="dbDataSource" class="org.springframework.jndi.JndiObjectFactoryBean">
    <beans:property name="jndiName" value="java:comp/env/jdbc/MyLocalDB"/>
</beans:bean>

### 39. Каким образом можно управлять транзакциями в Spring?
Транзакциями в Spring управляют с помощью Declarative Transaction Management (программное управление). Используется аннотация @Transactional для описания необходимости управления транзакцией. В файле конфигурации нужно добавить настройку transactionManager для DataSource.

<bean id="transactionManager"
    class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
    <property name="dataSource" ref="dataSource" />
</bean>

<bean id="transactionManager"
    class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
    <property name="dataSource" ref="dataSource" />
</bean>
### 40. Расскажите о Spring DAO.
Spring DAO предоставляет возможность работы с доступом к данным с помощью технологий вроде JDBC, Hibernate в удобном виде. Существуют специальные классы: JdbcDaoSupport, HibernateDaoSupport, JdoDaoSupport, JpaDaoSupport.

В Spring DAO поддерживается иерархия исключений, что помогает не обрабатывать некоторые исключения.

import java.util.List;
import org.springframework.jdbc.core.support.JdbcDaoSupport;
 
public class PersonDao extends JdbcDaoSupport{
 
public void insert(Person person){
String insertSql ="INSERT INTO PERSON (NAME, EMAIL) VALUES(?,?);";
String name = person.getName();
String email = person.getEmail();
 
getJdbcTemplate().update(insertSql,new Object[]{name,email});
}
 
public List<Person> selectAll(){
String selectAllSql = "SELECT * FROM PERSON;";
 
return getJdbcTemplate().query(selectAllSql, new PersonRowMapper());
}
 
}


import java.util.List;
import org.springframework.jdbc.core.support.JdbcDaoSupport;
 
public class PersonDao extends JdbcDaoSupport{
 
public void insert(Person person){
String insertSql ="INSERT INTO PERSON (NAME, EMAIL) VALUES(?,?);";
String name = person.getName();
String email = person.getEmail();
 
getJdbcTemplate().update(insertSql,new Object[]{name,email});
}
 
public List<Person> selectAll(){
String selectAllSql = "SELECT * FROM PERSON;";
 
return getJdbcTemplate().query(selectAllSql, new PersonRowMapper());
}
 
}
### 41. Как интегрировать Spring и Hibernate?
Для интеграции Hibernate в Spring необходимо подключить зависимости, а так же настроить файл конфигурации Spring. Т.к. настройки несколько отличаются между проектами и версиями, то смотрите официальную документацию Spring и Hibernate для уточнения настроек для конкретных технологий.

Читайте (spring 4, hibernate 5) –  Spring Data JPA — пример приложения Hello World. Настройки Spring Data + JPA + Hibernate + MySQL.

### 42. Расскажите о Spring Security.
Проект Spring Security предоставляет широкие возможности для защиты приложения. Кроме стандартных настроек для аутентификации, авторизации и распределения ролей и маппинга доступных страниц, ссылок и т.п., предоставляет защиту от различных вариантов атак (например CSRF). Имеет множество различных настроек, но остается легким в использовании.

Смотрите различные статьи в разделе Spring Security.

### 43. Как внедрить java.util.Properties в Spring Bean?
Для возможности использования Spring EL для внедрения свойств (properties) в различные бины необходимо определить propertyConfigure bean, который будет загружать файл свойств.

<bean id="propertyConfigurer"
  class="org.springframework.context.support.PropertySourcesPlaceholderConfigurer">
    <property name="location" value="/WEB-INF/application.properties" />
</bean> 
 
<bean class="com.journaldev.spring.EmployeeDaoImpl">
    <property name="maxReadResults" value="${results.read.max}"/>
</bean>

<bean id="propertyConfigurer"
  class="org.springframework.context.support.PropertySourcesPlaceholderConfigurer">
    <property name="location" value="/WEB-INF/application.properties" />
</bean> 
 
<bean class="com.journaldev.spring.EmployeeDaoImpl">
    <property name="maxReadResults" value="${results.read.max}"/>
</bean>
Или через аннотации:

@Value("${maxReadResults}") 
private int maxReadResults;
1
2
@Value("${maxReadResults}") 
private int maxReadResults;
### 44. Назовите некоторые из шаблонов проектирования, используемых в Spring Framework?
Spring Framework использует множество шаблонов проектирования, например:

Singleton Pattern: Creating beans with default scope.
Factory Pattern: Bean Factory classes
Prototype Pattern: Bean scopes
Adapter Pattern: Spring Web and Spring MVC
Proxy Pattern: Spring Aspect Oriented Programming support
Template Method Pattern: JdbcTemplate, HibernateTemplate etc
Front Controller: Spring MVC DispatcherServlet
Data Access Object: Spring DAO support
Dependency Injection and Aspect Oriented Programming
### 45. Best Practices в Spring Framework.
+ Избегайте указания версий в пространстве имен, чтобы быть уверенным в использовании последних версий.
+ Разделяйте конфигурации спринг согласно их деятельности, например: spring-jdbc.xml, spring-security.xml.
+ Spring бины, которые будут использованы в различных контекстах, необходимо указывать в root context и инициализировать с помощью listener.
+ Настраивайте зависимости бинов где это возможно и избегайте автоматического связывания там, где в этом нет строгой надобности.
+ Создавайте файл свойств и считывайте его в файле конфигурации Spring для использования application level properties.
+ Для больших приложений предпочтительнее использовать настройки с помощью xml файлов конфигурации, а не аннотаций.
+ Используйте подходящие по смыслу аннотации при указании бина, например: @Service для классов бизнес логики и @Repository для классов для работы с данными.
+ Spring framework имеет в проекте множество модулей. Удалите все лишние зависимости, которые могут быть загружены автоматически при указании корневой библиотеки.
+ Если вы используете аспекты, убедитесь, что используете точку присоединения как можно более близко, чтобы избежать случайных проблем с обработкой лишних методов. 
+ Пользовательские аннотации могут принести существенные преимущества при использовании AOP.
+ Используйте dependency injection там, где это принесет явную пользу. Внедрение зависимостей повсюду может добавить сложностей при поддержке проекта.
  
### 1 Для чего нужен Component Scan?
Если вы понимаете как работает Component Scan, то вы понимаете Spring
Первый шаг для описания Spring Beans это добавление аннотации — @Component, или @Service, или @Repository.
Однако, Spring ничего не знает об этих бинах, если он не знает где искать их. То, что скажет Spring где искать эти бины и называется Component Scan. В @ComponentScan вы указываете пакеты, которые должны сканироваться.
Spring будет искать бины не только в пакетах для сканирования, но и в их подпакетах.
### 2 Как вы добавите Component Scan в Spring Boot?
@SpringBootApplication
public class Application {
    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
}

@SpringBootApplication определяет автоматическое сканирование пакета, где находится класс Application

Всё будет в порядке, ваш код целиком находится в указанном пакете или его подпакетах.
Однако, если необходимый вам компонент находится в другом пакете, вы должны использовать дополнительно аннотацию @ComponentScan, где перечислите все дополнительные пакеты для сканирования

### 3 В чём отличие между @Component и @ComponentScan?
@Component и @ComponentScan предназначены для разных целей


@Component помечает класс в качестве кандидата для создания Spring бина.
@ComponentScan указывает где Spring искать классы, помеченные аннотацией @Component или его производной


### 4 Для чего используется аннотация @Bean?
В классах конфигурации Spring, @Bean используется для определения компонентов с кастомной логикой.


### 5 В чём разница между @Bean и @Component?
@Bean используется в конфигурационных классах Spring. Он используется для непосредственного создания бина.


@Component используется со всеми классами, которыми должен управлять Spring. Когда Spring видит класс с @Component, Spring определяет этот класс как кандидата для создания bean.


### 6 В чём разница между @Component, @Service и @Repository аннотациями?
Все они определяют бины Spring. Однако между ними всё же есть разница.


@Component — универсальный компонент
@Repository — компонент, который предназначен для хранения, извлечения и поиска. Как правило, используется для работы с базами данных.
@Service — фасад для некоторой бизнес логики


Пользовательские аннотации, производные от @Component, могут добавлять специальную логику в бинах.


Например, бины, получившиеся при помощи @Repository, дополнительно имеют обработку для JDBC Exception


### 7 Можем ли мы использовать @Component вместо @Service для бизнес логики?
Да. конечно.


Если @Component является универсальным стереотипом для любого Spring компонента, то @Service в настоящее время является его псевдонимом. Однако, в официальной документации Spring рекомендуется использовать именно @Service для бизнес логики. Вполне возможно, что в будущих версиях фреймворка, для данного стереотипа добавится дополнительная семантика, и его бины станут обладать дополнительной логикой.


### 8 В чем различие между web.xml и the Spring Context - servlet.xml?
web.xml — Метаданные и конфигурация любого веб-приложения, совместимого с Java EE. Java EE стандарт для веб-приложений.
servlet.xml — файл конфигурации, специфичный для Spring Framework.


### 9 Что предпочитаете использовать для конфигурации Spring - xml или аннотирование?
Предпочитаю аннотации, если кодовая база хорошо описывается такими элементами, как @Service, @Component, @Autowired


Однако когда дело доходит до конфигурации, у меня нет каких-либо предпочтений. Я бы оставил этот вопрос команде.


### 10 Можем ли мы применить @Autowired с не сеттерами и не конструкторами методами?
Да, конечно.


@Autowired может использоваться вместе с конструкторами, сеттерами или любым другими методами. Когда Spring находит @Autowired на методе, Spring автоматически вызовет этот метод, после создания экземпляра бина. В качестве аргументов, будут подобраны подходящие объекты из контекста Spring.


### 11 В чем разница между Сквозной Функциональностью (Cross Cutting Concerns) и АОП (аспектно оринтированное программирование)?
Сквозная Функциональность — функциональность, которая может потребоваться вам на нескольких различных уровнях — логирование, управление производительностью, безопасность и т.д.
АОП — один из подходов к реализации данной проблемы


### 12 В чем разница между IOC (Inversion of Control) и Application Context?
IOC — инверсия управления. Вместо ручного внедрения зависимостей, фреймворк забирает ответственность за это.
ApplicationContext — реализация IOC спрингом.


Bean Factory — это базовая версия IOC контейнера


Application Context также включает дополнительные функции, которые обычно нужны для разработки корпоративных приложений


### 13 В чем разница между classPathXmlApplicationContext и annotationConfigApplicationContext?
classPathXmlApplicationContext — если вы хотите инициализировать контекст Spring при помощи xml
annotationConfigApplicationContext — если вы хотите инициализировать контекст Spring при помощи конфигурационного класса java


### 14 Почему возвращаемое значение при применении аспекта @Around может потеряться? Назовите причины.
Метод, помеченный аннотацией @Around, должен возвращать значение, которое он (метод) получил из joinpoint.proceed()


@Around("trackTimeAnnotation()")
public Object around(ProceedingJoinPoint joinPoint) throws Throwable{
    long startTime = System.currentTimeMillis();
    Object retVal = joinPoint.proceed();
    long timeTaken = System.currentTimeMillis() - startTime;
    logger.info("Time taken by {} is equal to {}",joinPoint, timeTaken);
    return retVal;
}

### 15 Как вы решаете какой бин инжектить, если у вас несколько подходящих бинов. Расскажите о @Primary и @Qualifier?
Если есть бин, который вы предпочитаете большую часть времени по сравнению с другими, то используйте @Primary, и используйте @Qualifier для нестандартных сценариев.


Если все бины имеют одинаковый приоритет, мы всегда будем использовать @Qualifier


Если бин надо выбрать во время исполнения программы, то эти аннотации вам не подойдут. Вам надо в конфигурационном классе создать метод, пометить его аннотацией @Bean, и вернуть им требуемый бин.


### 16 Что нового в Spring Framework 5.0?
На мой взгляд это Functional Web Framework, Kotlin и и поддержка реактивного программирования.


### 17 Сравните Application Context, IOC Container, vs Web Container и EJB Container. Нужен ли Web Container для запуска Spring Boot приложения?
Web Container и EJB Containers являются частью приложения/веб-сервера, таких как Tomcat, Websphere, Weblogic. Они добавляют свою дополнительную функциональность к ним. Java EE определяет контракт для веб-приложений, эти контейнеры являются реализацией этих контрактов.


Spring контейнер может являться частью любого приложения, которое вы делаете на java. Spring может работать внутри веб-контейнера, ejb контейнера или даже без них.


### 18 Как мы можем выбрать подходящий бин при помощи application.properties?
Рассмотрим пример:


interface GreetingService {
    public String sayHello();
}

И два компонента


@Component(value="real")
class RealGreetingService implements GreetingService {
    public String sayHello() {
        return "I'm real";
    }
}

@Component(value="mock")
class MockGreetingService implements GreetingService {
    public String sayHello() {
        return "I'm mock";
    }
}

Тогда в application.properties добавим свойство
application.greeting: real


Воспользуемся данным решением:


@RestController
public class WelcomeController {
    @Resource(name="${application.greeting}")
    private GreeterService service1;
}

### 19 Какая минимальная версия Java поддерживается в Spring Boot 2 и Spring 5?
Spring 5.0 и Spring Boot 2.0 поддерживают Java 8 и более поздней версии.


### 20 В чём разница между @Controller и @RestController?
@RestController = @Controller + @ResponseBody


@RestController превращает помеченный класс в Spring-бин. Этот бин для конвертации входящих/исходящих данных использует Jackson message converter. Как правило целевые данные представлены в json или xml.


### 21 Почему иногда мы используем @ResponseBody, а иногда ResponseEntity?
ResponseEntity необходим, только если мы хотим кастомизировать ответ, добавив к нему статус ответа. Во всех остальных случаях будем использовать @ResponseBody.


@GetMapping(value=”/resource”) 
@ResponseBody 
public Resource sayHello() { return resource; }

@PostMapping(value=”/resource”) 
public ResponseEntity createResource() { 
    ….
return ResponseEntity.created(resource).build(); 
}

Стандартные HTTP коды статусов ответов, которые можно использовать.
200 — SUCCESS
201 — CREATED
404 — RESOURCE NOT FOUND
400 — BAD REQUEST
401 — UNAUTHORIZED
500 — SERVER ERROR


Для @ResponseBody единственные состояния статуса это SUCCESS(200), если всё ок и SERVER ERROR(500), если произошла какая-либо ошибка.


Допустим мы что-то создали и хотим отправить статус CREATED(201). В этом случае мы используем ResponseEntity.


### 22 В чем разница между Filters, Listeners and Interceptors?
Концептуально всё просто, фильтры сервлетов могут перехватывать только HTTPServlets. Listeners могут перехватывать специфические события. Как перехватить события которые относятся ни к тем не другим?


Фильтры и перехватчики делают по сути одно и тоже: они перехватывают какое-то событие, и делают что-то до или после.


Java EE использует термин Filter, Spring называет их Interceptors.


Именно здесь AOP используется в полную силу, благодаря чему возможно перехватывание вызовов любых объектов


### 23 В чем разница между ModelMap и ModelAndView?
Model — интерфейс, ModelMap его реализация..


ModelAndView является контейнером для пары, как ModelMap и View.


Обычно я люблю использовать ModelAndView. Однако есть так же способ когда мы задаем необходимые атрибуты в ModelMap, и возвращаем название View обычной строкой из метода контроллера.


### 24 В чем разница между model.put() и model.addAttribute()?
Метод addAttribute отделяет нас от работы с базовой структурой hashmap. По сути addAttribute это обертка над put, где делается дополнительная проверка на null. Метод addAttribute в отличии от put возвращает modelmap.
model.addAttribute(“attribute1”,”value1”).addAttribute(“attribute2”,”value2”);


### 25 Что можете рассказать про Form Binding?
Нам это может понадобиться, если мы, например, захотим взять некоторое значение с HTML страницы и сохранить его в БД. Для этого нам надо это значение переместить в контроллер Спринга.


Если мы будем использовать Spring MVC form tags, Spring автоматически свяжет переменные на HTML странице с Бином Спринга.


Если мне придется с этим работать, я обязательно буду смотреть официальную документацию Spring MVC Form Tags.


### 26 Почему мы используем Hibernate Validator?
Hibernate Validator никак не связан с БД. Это просто библиотека для валидации.


Hibernate Validator версии 5.x является эталонной реализацией Bean Validation 1.1


Так же если взглянуть по адресу http://beanvalidation.org/2.0, то Hibernate Validator является единственным, который сертифицирован.


### 27 Где должны располагаться статические (css, js, html) ресурсы в Spring MVC приложении?
Расположение статических ресурсов можно настроить. В документации Spring Boot рекомендуется использовать /static, или /public, или /resources, или /META-INF/resources


### 28 Почему для конфиденциальных данных рекомендуется использовать POST, а не GET запросы?
В случае GET запроса передаваемые параметры являются частью url, и все маршрутизаторы, через которые пройдет наш GET запрос, смогут их прочитать.


В случае POST запроса передаваемые параметры являются частью тела запроса. При использовании HTTPs, тело запроса шифруется. Следовательно, использование POST запросов является более безопасным


### 29 Можно ли передать в запросе один и тот же параметр несколько раз?
Пример:
http://localhost:8080/login?name=Ranga&name=Ravi&name=Sathish
Да, можно принять все значения, используя массив в методе контроллера


public String method(@RequestParam(value="name") String[] names){   
}
