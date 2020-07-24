# Auto Mapper

Performs mapping one object to another.

### Use Example

```csharp
EPerson person = new EPerson();

            person.firstName = "test name";
            person.lastName = "test surname";
            person.number = "test number";
            person.code = "test code";

            var config = new MapperConfiguration(cfg => { cfg.CreateMap<EPerson, EEmployee>()
                .ForMember(x => x.serialNr, y =>y.MapFrom(x => x.code))
                ; });

            IMapper mapper = config.CreateMapper();

            var dest = mapper.Map<EPerson, EEmployee>(person);
```
