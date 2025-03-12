README
-------------
Can be ran Via any browser.

Requirements:
1.a web browser
2.CORS permissions( for spring app refer below class)

----------------------------------------------------------
@Configuration
public class WebConfig implements WebMvcConfigurer {

    @Override
    public void addCorsMappings(CorsRegistry registry) {
        registry.addMapping("/**")
                .allowedOrigins("*")  // Allow all origins (use carefully)
                .allowedMethods("GET", "POST", "PUT", "DELETE", "OPTIONS")
                .allowedHeaders("*");
    }
}
//add to existing spring project -> open "postman-ripoff.html" and use,
 no app,JSON script, curl setup or admin access required. 
------------------------------------------------------------

NOTE : DESIGNED FOR BASIC TESTS DO NOT ADD CORSMAPPINGS IN ANY PROD APPS.