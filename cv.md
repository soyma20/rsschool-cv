# Soima Yaroslav

********* 

### Contacts

Email - **slaviksoyma2014@gmail.com**  
Telegram - **soyma20**  
[LinkedIn](https://www.linkedin.com/in/yaroslav-soima-48294824a/)  
Phone number **+380982979504**
********* 

### Brief information about myself

I`m looking for a position of *junior full-stack developer* or *junior front-end developer* or *junior back-end
developer*. I am ready to study and increase any reasonable, practical and creative ideas. I am responsible and
hard-working person. A quick learner who absorbs new ideas and can
communicate clearly and effectively with people from all social and professional backgrounds. Wellmannered and flexible
in the ability to adapt to challenges when they arise.
********* 

### Skills

1. HTML5
2. CSS
3. JavaScript
4. React.js
5. TypeScript
6. Angular.js
7. MySQL
8. MongoDB
9. Java
10. Hibernate
11. Spring

********* 

### Code examples

##### Vanila JS Fetching
```
let usersDiv = document.createElement('div');
usersDiv.classList.add('users')
document.body.appendChild(usersDiv)
fetch('https://jsonplaceholder.typicode.com/users')
    .then(value => value.json())
    .then(users =>{
        for (let user of users) {
            let userConteiner = document.createElement('div');
            userConteiner.classList.add('user');
            userConteiner.innerHTML = `
                <h3>${user.username}</h3>
                <h4>${user.name}</h4>`
            let button = document.createElement('button');
            let link = document.createElement('a');
            link.innerText = 'User details';
            link.href = `./user-details.html?data=${JSON.stringify(user)}`;
            button.appendChild(link);
            userConteiner.appendChild(button);
            usersDiv.appendChild(userConteiner);
        }
    })
```
##### React Authorization Service
```
import {axiosService} from "./axios.service";

import {urls} from "../constants";

const authService = {
    getTokens:(user)=> axiosService.post(urls.auth, user),
    refresh:(refresh)=>axiosService.post(`${urls.auth}/refresh`, {refresh} )
}

export {
    authService
}
```
##### Angular Resolver
```
@Injectable({
  providedIn: 'root'
})
export class MoviesResolver implements Resolve<IResponseMovie>{
  pageForService:number;

  constructor(private movieService: MoviesService, private activatedRoute: ActivatedRoute) {
  }

  resolve(route: ActivatedRouteSnapshot, state: RouterStateSnapshot): Observable<IResponseMovie> | Promise<IResponseMovie> | IResponseMovie {
    return this.movieService.getAll(this.pageForService);
  }


}
```
##### Java Security Config
```

@Configuration
@EnableWebMvc
@AllArgsConstructor
public class SecurityConfig extends WebSecurityConfigurerAdapter {

    private CustomerDao customerDao;

    @Bean
    public PasswordEncoder passwordEncoder() {
        return new BCryptPasswordEncoder();
    }

    @Override
    protected void configure(AuthenticationManagerBuilder auth) throws Exception {
        auth.userDetailsService(username -> {
            Customer customer = customerDao.findByLogin(username);
            return new User(
                    username,
                    customer.getPassword(),
                    customer.getRoles().stream().map(role -> new SimpleGrantedAuthority(role.name())).collect(Collectors.toList())
            );
        });
    }

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http.csrf().disable()
                .authorizeHttpRequests()
                .antMatchers(HttpMethod.GET, "/").permitAll()
                .antMatchers(HttpMethod.POST, "/").hasRole("ADMIN")
                .antMatchers(HttpMethod.GET, "/customers").hasAnyRole("ADMIN", "MANAGER", "USER")
                .antMatchers(HttpMethod.POST, "/customers").permitAll()
                .and()
                .httpBasic().and()
                .sessionManagement().sessionCreationPolicy(SessionCreationPolicy.STATELESS).and()
                .cors().configurationSource(corsConfigurationSource()).and();

//                .and()
//                .addFilterBefore((servletRequest, servletResponse, filterChain) -> filterChain.doFilter(servletRequest,servletResponse),
//                        UsernamePasswordAuthenticationFilter.class);

    }

    @Bean
    CorsConfigurationSource corsConfigurationSource() {
        CorsConfiguration configuration = new CorsConfiguration();

        configuration.setAllowedOrigins(Arrays.asList("http://localhost:4200", "http://localhost:3000"));
        configuration.addAllowedHeader("*");
        configuration.setAllowedMethods(Arrays.asList(
                HttpMethod.GET.name(),
                HttpMethod.POST.name(),
                HttpMethod.PATCH.name(),
                HttpMethod.PUT.name(),
                HttpMethod.DELETE.name()
        ));
        configuration.addExposedHeader("Authorization");

        UrlBasedCorsConfigurationSource source = new UrlBasedCorsConfigurationSource();
        source.registerCorsConfiguration("/**", configuration);
        return source;
    }
}
```

********* 

### Experience

1. [Front-end project for Zoo at RS school realized on vanilla JS (currently working with)](https://github.com/rolling-scopes-school/soyma20-JSFE2022Q3/tree/online-zoo)
2. [Front-end project on **JSONPlaceholder
   API** realized on vanilla JS](https://github.com/soyma20/normal_JS/tree/master/mini%20progect)
3. [Front-end project on **Rick and Morty
   API** realized on React.js](https://github.com/soyma20/react-apr-soyma20/tree/RickAndMortyApi)
3. [Front-end project on **Okten School
   API** realized on React.js with interceptors and authorization](https://github.com/soyma20/react-apr-soyma20/tree/bonus_authorization)
3. [Front-end project on **TMDB
   API** realized on Angular.js with  interceptors and authorization](https://github.com/soyma20/ng20222/tree/movieProgect)
3. [Back-end project on **Java realized on
   Spring** with security(authorization)](https://github.com/soyma20/ng20222/tree/movieProgect)
3. [Back-end project on **Java realized on
   Spring** AutoRia clone (currently working with)](https://github.com/soyma20/ng20222/tree/movieProgect)

********* 

### Education

##### Kolomiya College of Economics and Law

September 2016 – June 2019  
**Junior specialist**, «Business, trade and exchange activity/Commodity research and
commerce»

##### Kyiv National University of Trade and Economics.

September 2019 – June 2021
**Bachelor**, «Business, trade and exchange activity/Customs affairs»

##### Kyiv National University of Trade and Economics.

September 2021 – December 2022
**Master**, «Business, trade and exchange activity/Customs affairs»

##### RS School

September 2022 – present
«JavaScript/Front-end 2022Q3»

#### Green Forest

September 2020 - July 2021
«English courses A2-B1»
********* 

### Languages

1. Ukrainian - native
2. Russian - fluent
3. English - B1

I have been studied English in Green Forest for **9 months** on daily basis, on Mondays, Wednesdays and Fridays. I
participated
with other students in discussions of lesson`s main topic and grammar quizes, for instance, Kahoot, Alias. The other
days I engaged in self-education by doing the courses homework and additional tasks.

