# springboot-kafka
Spring Boot2.0 整合 Kafka

## 安装配置Kafka ,Zookeeper
在这里不再赘述，可参考[Apache Kafka 安装步骤](https://www.w3cschool.cn/apache_kafka/apache_kafka_installation_steps.html)

## 执行测试类可查看效果
```java
    @Test
    public void kafkaSend() throws InterruptedException {
        //模拟发消息
        for (int i = 0; i < 5; i++) {
            User user = new User();
            user.setId(System.currentTimeMillis());
            user.setMsg(UUID.randomUUID().toString());
            user.setSendTime(new Date());

            kafkaSender.send(user);
            Thread.sleep(3000);
        }
    }
```

## 参考资料
[Spring Boot2.0 整合 Kafka](https://www.cnblogs.com/softmax/p/9414726.html)
