## API 컨벤션
### **1. URI 마지막 문자로 슬래시(/)를 포함하지 않는다.**

- 슬래시는 웹에서 디렉토리나 폴더를 나타낼 수 있다.
    - https://example.com/resource 는 리소스 자체를 의미하고, https://example.com/resource/ 는 리소스라는 디렉토리를 나타낸다.
    
    - 서버는 두 URI를 서로 다른 리소스로 받아들일 수 있다.
    
- REST API에서는 리소스의 집합을 나타낼때 슬래시를 포함할 수 있지만 개별 리소스를 나타낼때에는 슬래시를 사용하지않아야한다.
    - https//example.com/users/ 는 사용자들의 리스트나 집합을 반환하지만
    - https//example.com/users/123 은 특정 사용자, id 123
    - 을 나타낸다.
- URL 끝에 슬래시를 추가하면 서버에서 리다이렉션이 발생할 수 있다.
    - /resource 로 접근했을때 서버가 /resource/로 리다이렉션하거나 그 반대로 동작할수 있다. → 이러한 리다이렉션은 불필요한 요청을 발생시키며 응답시간이 증가하게한다. 검색 엔진 최적화에 영향을 미치게 된다.
- 슬래시가 없는 URI
    
    {  
     "id": “string”,  
     "name": "string",  
     "description": "string”  
    }
    
- 슬래시가 있는 URI
    
    [  
      {  
     "id": “string”,   
     "name": "string"  
    },  
    {   
"id": “string”,  
   "name": "string"  
     }  
    ]
    
### 2. **resource를 명사로 나타내야한다**
- resource는 수행되는 행위가 아니라 객체라 네가지 범주로 나누는게 좋다.
    - 문서(Document) : 단일개념으로 단수 사용
    - 컬렉션(Collection) : 서버가 관리하는 리소스 디렉토리를 나타내며 복수 사용
    - 스토어(Store) : 클라이언트가 관리하는 자원 저장소로 복수 사용
    - 컨트롤러(Controller) : 추가 프로세스를 실행해주는걸로 동사 사용
    
    → [http://api.example.com/](http://api.example.com/device-management)resource-management/managed-resources/chekout/{id}
    
### 3. **가독성을 위해 ‘_’는 사용하지 말아야 하며 ‘-’을 사용해야하며 소문자를 사용해야한다.**
