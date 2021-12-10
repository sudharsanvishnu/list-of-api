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
       <FlatList
                keyExtractor={(item, index) => index.toString()}
                showsHorizontalScrollIndicator={false}
                refreshing={true}
                maxToRenderPerBatch={10}
                initialNumToRender={7}
                data={news}
                renderItem={({ item }) => (
                        <View>
                              <Text>{item.API}</Text>
                              <Text>{item.Description}</Text>
                              <Text>{item.Auth}</Text>
                              <Text>{item.HTTPS}</Text>
                              <Text>{item.Cors}</Text>
                              <Text>{item.Link}</Text>
                              <Text>{item.Category}</Text>
                        </View>
               )}
              /> 
    </View>
    )
}
```

For more details see [React Native Docs](https://reactnative.dev/docs/network)


### Support or Contact

sudharsanvishnu@gmail.com
