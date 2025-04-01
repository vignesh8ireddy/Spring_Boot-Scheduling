# Spring_Boot-Scheduling

* Spring Boot Scheduling module is useful for executing given task/job for one or multiple times based on given
PERIOD OF TIME or POINT OF TIME.
  * Period of Time: specifies the gap between two successive executions of the task.
  * Point of Time: specifies the date, time of the task to be executed at.
* JDK API provides TimerTask and Timer classes of java.util package to perform scheduling based operations.
* In Spring Boot, once the spring-boot-starter dependency is added we get the support for scheduling.
  * spring-boot-starter dependency gives AutoConfiguration, dependent and related Spring jars, logging, scheduling, yml
  processing,...
* We add scheduling power to a spring boot application by adding the following annotations
  * @EnableScheduling annotation on the top of main class (i.e starter class) along with @SpringBootApplication.
  * In any spring bean class (i.e class with stereotype annotation) place business methods (should be 0-parametered)
  with @Scheduled annotation, for scheduling the business method.
* @Scheduled(initialDelay,fixedDelay/fixedRate/CRON)
* CRON expressions (6 * syntax)
  * [seconds, 0-59] [minutes, 0-59] [hours, 0-23] [date of month, 1-31] [month of year, 1-12] [week day, 0-7 or SUN-SAT]
  * / (period of time), * (all/any), , (list of values), - (range of values), ? (any, but can be used only in date, 
  weekday when month is specified)
  * From spring 5.3, the following were introduced to use in CRON expressions
    * L (last days info, can be used only in date, weekday)
    * W (weekdays info, can be used only in date, weekday)
    * @ (to work with macros, @yearly, @hourly, @daily,...)
    * #(combination symbol)
* 