# Configure Repo

### 1. Create a Dev environment
- Installed nodemon as **dev-dependency**
- Created the **dev** script in **package.json**

### 2. Create a repo
- Initialize GIT
- Add a Repo URL
- Create .gitignore file with content 

### 3. Implement the **useCachingFetch** hook
- State creation for **data**
> const [data, setData] = useState<unknown>([]);
- State creation for **isLoading**
> const [isLoading, setIsLoading] = useState<boolean>(true);
- State creation for **error**
> const [error, setError] = useState<Error | null>(null);

### 4. Create cache for service calls
- Create a singleton to store the data
> const cachedData: ICachedData = {};
- Consult the singleton onMount to bring data from cache or call the service
```Effect(() => {
  const data = cachedData[url];
  if (!!data) {
    setData(data);
    setIsLoading(false);
  } else load();
}, []);```
