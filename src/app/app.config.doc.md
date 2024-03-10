## Setting up the HttpClient by app.config

It's necesary add the provider to the file app.config.ts if you are not using modules approach for Angular version 17
src/app/app.config.ts

```
import { ApplicationConfig } from '@angular/core';
import { provideRouter } from '@angular/router';
import { routes } from './app.routes';
import { provideHttpClient } from '@angular/common/http';

export const appConfig: ApplicationConfig = {
  providers: [provideRouter(routes), provideHttpClient()]
};
```

If the request pass through the interceptor it's a mandatory to notify the provider in the route src/app/app.config.ts

```
provideHttpClient(withInterceptors(
  [firstInterceptor, secondInterceptor, thirdInterceptor]
))
```


<style>
  h2 {
    color: red;
  }
</style>