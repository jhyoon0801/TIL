# [Java] mybatis

##### TypeHandler
* POJO <-> DB Data 간 데이터 타입이 일치하지 않을 경우 사용
* Custom type handler를 사용하기 위해선 TypeHandler interface를 오버라이드하여 사용
    * TypeHandler interface를 직접 구현하기 보다는 BaseTypeHandler 클래스를 확장하여 사용하자
* 타입 명시
    * 아래 두 경우 모두 type handler의 엘리먼트 설정이 우선순위가 높음. 엘리먼트가 있으면 어노테이션은 무시
    *  DB Data 타입 명시
        * type handler의 엘리먼트(mybatisConfig.xml에서 실제 사용 시)에 jdbcType 속성 추가 ( ex] jdbcType="VARCHAR" )
        * TypeHandler클래스에 @MappedJdbcTypes 추가하고 파라미터 값으로 jdbc type 지정( ex] @MappedJdbcTypes(JdbcType.VARCHAR) )
    *  Java type 명시
        *  type handler의 엘리먼트(mybatisConfig.xml에서 실제 사용 시)에 javaType 속성 추가 ( ex] javaType="String" )
        *  TypeHandler클래스에 @MappedTypes 추가하고 파라미터 값으로 
java type 지정 ( ex] @MappedTypes(String.class) )
```
public abstract interface TypeHandler<T> {
    public abstract void setParameter(PreparedStatement paramPreparedStatement, int paramInt, T paramT, JdbcType paramJdbcType) throws SQLException;

    public abstract T getResult(ResultSet paramResultSet, String paramString) throws SQLException;

    public abstract T getResult(ResultSet paramResultSet, int paramInt) throws SQLException;

    public abstract T getResult(CallableStatement paramCallableStatement, int paramInt) throws SQLException;
}
```

### ref 
1. http://www.mybatis.org/mybatis-3/ko/configuration.html#typeHandlers
2. http://mybatis-user.963551.n3.nabble.com/How-to-use-custom-type-handler-td4027193.html
3. http://antop.tistory.com/140