# pngen
票牛代码生成器修复版
原版的票牛代码生成器，无法在idea2020版使用，并且在非Java文件上也会显示"Convert Java entity to create table sql"，此版本为修复了这两个问题的版本。


使用方法：
在Java实体类上右键—>"Convert Java entity to create table sql"，就可以生成Mysql的SQL语句

Java实体类：
```
@Getter
@Setter
@Entity(name = "shop")
public class shop  {

    @Id
    @Column(name = "id")
    private Long id;

    /**
     * 用户名
     */
    @Column(name = "username")
    private String username;

    /**
     * 密码
     */
    @Column(name = "password")
    private String password;

    /**
     * 角色
     */
    @Column(name = "role")
    private String role;

    /**
     * 权限
     */
    @Column(name = "permission")
    private String permission;

    /**
     * 备注
     */
    @Column(name = "remark")
    private String remark;
}
```

生成的SQL：
```
CREATE TABLE `shop` (
`id` bigint(20) NOT NULL ,
`username` VARCHAR(255) NOT NULL COMMENT '用户名',
`password` VARCHAR(255) NOT NULL COMMENT '密码',
`role` VARCHAR(255) NOT NULL COMMENT '角色',
`permission` VARCHAR(255) NOT NULL COMMENT '权限',
`remark` VARCHAR(255) NOT NULL COMMENT '备注',
PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
```
