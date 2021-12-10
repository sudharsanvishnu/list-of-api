## LIST OF PUBLIC API

Go to https://sudharsanvishnu.github.io/list-of-api/API.Json 

### FETCH API

This API provided the list of public API example 
```
      {
         "API": "AdoptAPet",
         "Description": "Resource to help get pets adopted",
         "Auth": "apiKey",
         "HTTPS": true,
         "Cors": "yes",
         "Link": "https://www.adoptapet.com/public/apis/pet_list.html",
         "Category": "Animals"
      },
      
```

Example Fetch API using React native
```markdown

const API_KEY = "https://sudharsanvishnu.github.io/list-of-api/API.Json"

const App = () => {

  const [data, setData ] = useState([]);

  useEffect(() => {
          const controller = new AbortController();
          const  signal  = controller.signal;      
          (async () => {
            const response = await fetch(API_KEY, {signal});
              const data = await response.json();
                setData(data.entries); // fetched JSON
            }
          )();
          
          return () => controller.abort();
   },[API_KEY])
  
    return(
    <View>
      <Text>{data.API}</Text>
      <Text>{data.Description}</Text>
      <Text>{data.Auth}</Text>
      <Text>{data.HTTPS}</Text>
      <Text>{data.Cors}</Text>
      <Text>{data.Link}</Text>
      <Text>{data.Category}</Text>
    </View>
    )
}
```

For more details see [React Native Docs](https://reactnative.dev/docs/network)


### Support or Contact

sudharsanvishnu@gmail.com
