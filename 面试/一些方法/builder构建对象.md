```java
// package whatever; // don't place package name!

import java.io.*;
import java.util.*;
import java.lang.*;

class MyCode {

    public static void main(String[] args){
        // Question: Implement the Company Class so we can set the field like below:
        Company antra = Company.builder().name("Antra").address("Virginia").createdTime(new Date()).sizeOfEmployee(300).contact("12345").build();
        System.out.print(antra); // Output: Company{name='antra', address='Virginia', contact='12345', sizeOfEmployee=300, createdTime=Wed Oct 21 11:50:41 EDT 2020}
        
        Company apple = Company.builder().name("Apple").build();
        System.out.println(apple); // Company{name='Apple', address='null', contact='null', sizeOfEmployee=0, createdTime=null}
    }
}

class Company {
    private final String name;
    
    private String address;
    private Date createdTime;
    private String contact;
    private Integer sizeOfEmployee;
    
    public static Builder builder(){
      return new Builder();
    }
    
    private Company(Builder builder){
      this.name = builder.name;
      this.address = builder.address;
      this.createdTime = builder.createdTime;
      this.sizeOfEmployee = builder.sizeOfEmployee;
      this.contact = builder.contact;
    }
    
    public static class Builder{
      private String name;
    
      private String address;
      private Date createdTime;
      private String contact;
      private Integer sizeOfEmployee;
      
      public Builder(){
        //this.name = name;
      }
      public Builder name(String name){
        this.name = name;
        return this;
      }
      public Builder address(String address){
        this.address = address;
        return this;
      }
      public Builder createdTime(Date createdTime){
        this.createdTime = createdTime;
        return this;
      }
      public Builder sizeOfEmployee (int sizeOfEmployee){
        this.sizeOfEmployee = sizeOfEmployee;
        return this;
      }
      public Builder contact (String contact){
        this.contact = contact;
        return this;
      }
      
      public Company build(){
        return new Company(this);
      }
    }
    
    @Override
    public String toString() {
        return "Company{" +
                "name='" + name + '\'' +
                ", address='" + address + '\'' +
                ", contact='" + contact + '\'' +
                ", sizeOfEmployee=" + sizeOfEmployee +
                ", createdTime=" + createdTime +
                '}';
    }
    
    
}

```

