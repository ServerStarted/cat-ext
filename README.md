### cat 的扩展包

#### druid 加入cat filter

在druid 数据库连接配置中，加入 DruidCatFilter，如：

```xml
  <bean id="dataSource" class="com.alibaba.druid.pool.DruidDataSource"
    init-method="init" destroy-method="close">
    <property name="url" value="${database/service/user/jdbc/url}" />
    <property name="username" value="${database/service/user/username}" />
    <property name="password" value="${database/service/user/password}" />
    <property name="initialSize" value="1" />
    <property name="minIdle" value="1" />
    <property name="maxActive" value="20" />
    <property name="maxWait" value="60000" />
    <property name="timeBetweenEvictionRunsMillis" value="60000" />
    <property name="minEvictableIdleTimeMillis" value="300000" />
    <property name="validationQuery" value="SELECT 1" />
    <property name="testWhileIdle" value="true" />
    <property name="testOnBorrow" value="false" />
    <property name="testOnReturn" value="false" />
    <property name="poolPreparedStatements" value="false" />
    <property name="maxPoolPreparedStatementPerConnectionSize"
      value="20" />
    <property name="proxyFilters">
      <list>
        <bean class="com.serverstarted.cat.ext.druid.DruidCatFilter" />
      </list>
    </property>
  </bean>
```