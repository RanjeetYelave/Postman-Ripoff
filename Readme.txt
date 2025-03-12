
# Postman Ripoff

A simple web-based API testing tool that mimics Postman functionality. This tool can be used to send GET, POST, and DELETE requests to any API and view the response directly in your browser.

---

## Requirements

1. **A Web Browser**  
   This tool can be run in any modern web browser (e.g., Chrome, Firefox, Safari, etc.).

2. **CORS Permissions**  
   If you are using a Spring-based backend for testing APIs, you will need to ensure CORS (Cross-Origin Resource Sharing) permissions are configured properly on your Spring application.

---

## CORS Configuration for Spring Applications

If you're using a Spring Boot application, you need to configure CORS permissions. Below is the Spring `WebConfig` class to allow CORS for your API endpoints:

```java
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
```

This will allow your frontend (Postman Ripoff) to communicate with the backend APIs without any CORS-related issues.

**Note:**  
- **DO NOT** use this CORS configuration in a production environment, as it allows all origins (`allowedOrigins("*")`). For production, it's recommended to restrict this to trusted domains.

---

## How to Use

1. **Download or Open `postman-ripoff.html`**  
   Simply open the `postman-ripoff.html` file in your preferred browser.

2. **Send API Requests**  
   - Input your API URL in the provided text field.
   - Select the type of request: GET, POST, or DELETE.
   - For POST and DELETE requests, provide the request body in the `JSON Body` text area.
   - Click the "Send Request" button to initiate the API request.

3. **View API Responses**  
   Once the request is sent, the response will appear below, including the status and returned data (if any). You will also see a progress bar and a success tick once the request completes.

---

## Notes

- **No Application Setup Required**:  
  This tool is designed to be opened directly in the browser. No additional setup (such as JSON scripts, curl setup, or admin access) is required.

- **Designed for Basic Testing**:  
  This tool is intended for quick, manual API testing only. It is **NOT** designed for production or heavy testing environments.

- **CORS in Production**:  
  If you use CORS in your production environment, please make sure to set proper security measures and limit the allowed origins to trusted domains.

---

## License

This project is open source and available under the [MIT License](LICENSE).
