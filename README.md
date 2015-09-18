# Merona.Paop.cs
Merona.Paop.cs is a set of useful __Aspects__, using Merona's Packet-AOP Feature<BR>
paohukumchukkumchuk

[Restriction]
패킷의 필드에 제약 조건을 설정할 수 있습니다.
```c#
[Restriction (Range = [6, 16])]
public String name;
```
```c#
[Restriction (Equal = "ASDF")]
public String name;
```

[Log]
Log Aspect는 전체 패킷 또는 단일 필드에 대해서 로그를 남길 수 있도록 해줍니다.
```c#
[Log]
class SomePacket : Packet {
}
```

단일 필드에 Log를 사용할 때는 조건을 지정할 수 있습니다.<br>
이 기능을 사용하면 필드가 특정 조건을 달성할 때만 로깅하여, 편리한 모니터링 환경을 구성할 수 있습니다.
```c#
[Log(Equal = true)]
public bool v; 
```


[Mock]
이전에 어떤 값이 들어있든 상관 없이 무조건 지정된 값으로 필드를 덮어씁니다.<br>
이 기능은 개발 시 가벼운 수정 사항이 있을 때, 클라이언트 수정 없이 디버깅을 가능하도록 해 줍니다.
```c#
[Mock(1234)]
public int value;
```

[Sha256]
필드를 Sha256 암호화합니다.
```c#
[Sha256]
public String password;
```
