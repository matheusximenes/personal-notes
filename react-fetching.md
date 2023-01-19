# RTK Query, React Query, and SWR (Promise Watchers)


## Axios Library:
- Docs: https://www.npmjs.com/package/axios?activeTab=readme
- Note: Returns a JSON already
- e.g.:
    ```const controller = new AbortController();
    async function getUser() {
        try {
            const response = await axios.get('/user?ID=12345', {
            signal: controller.signal
            });
            console.log(response);
        } catch (error) {
            console.error(error);
        }
    }
- Feature Axios.create() and create a single API/Endpoints File

## RTK Query (Redux React Toolkit):
  - What is:
      * Fetching Watcher and Caching tool
  - Motivation:
      * Tracking Loading state
      * Avoid Duplicate Request
      * Managing Cache - Websockets

  - Creating:
      * Create a apiSlice in 'services' or 'features/api' folder
      * Export the builder query by 'use<QueryName>Query/Mutation destructuring from 'apiSlice' on the endpoints
          - build.query is for fetching and build.mutation is for *'POST', 'PUT', 'PATCH', and 'DELETE'* requests
          *** for Cache use TagTypes
          -  Typescript builder.query|mutation<Return value, Mutation body|void>
      * Component:
          - Query ==> `const { data: <QueryName>, isLoading, isSuccess, isError, error } = use<QueryName>Query();`
          - Mutation ==> `const [<MutationName>, {isLoading, isError, error }] = use<MutationName>Mutation()`

## React Query (TanStack)
  - What is: fetching, caching, synchronizing and updating server state in your React applications a breeze
  - Motivation: Manage Server State and Caching Queries, Canceling multiple requests
  - Usage:
      * App.js ==> Wrap the Application on a 'QueryClientProvider' with client = new QueryClient()
      * Component:   
          - Query --> use hook 'useQuery' giving a name to the query the return a promise receive { isLoading (boolean), error (Obj), data (any) ... }
          - Mutation --> use hook 'useMutation' giving a name to the query the return a promise receive { mutate, isLoading (boolean), error (Obj), data (any) ... }

* ASWr (Learn More)