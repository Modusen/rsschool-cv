# **Astrashenya Dmitry**

## Contacts

- _Location:_ St.Petersburg, Russia
- _Email:_ AstrashenyaD@ya.ru
- _Telegram:_ @DmitriyAstrashenya
- _[GitHub](https://github.com/modusen)_

## About Me

_Hello everyone! My name is Dmitriy. I am a Java developer. I am really glad and so excited to start learning JS._

## Skills

- _Java 8+._
- _Spring (Boot, Data JPA, MVC, Security etc.)_
- _PostgreSQL, Oracle._
- _MongoDb, Redis._
- _Vaadin._
- _Kafka._
- _Microservices._
- _HTML&CSS basics._

## Code examples

```
@Service
public class MessageServiceImpl implements MessageService {
    private final Logger logger = LoggerFactory.getLogger(MessageServiceImpl.class);
    private final RestTemplate restTemplate = new RestTemplate();
    @Value("${vk_bot_token}")
    private String token;
    @Value("${callback_API_version}")
    private String version;

    public void sendMessageInResponse(Message message) {
        String url = "https://api.vk.com/method/messages.send?";

        try {
            URI uri = new URIBuilder(url)
                    .addParameter("message", "Вы сказали: " + message.getText())
                    .addParameter("peer_id", String.valueOf(message.getPeerId()))
                    .addParameter("access_token", token)
                    .addParameter("v", version)
                    .addParameter("random_id", "0")
                    .build();
            ResponseEntity<?> response = restTemplate.postForEntity(uri, null, String.class);

            if (response.getStatusCode() == HttpStatusCode.valueOf(200)) {
                logger.info("Response body: \r\n" + response.getBody());
            }

        } catch (URISyntaxException e) {
            logger.error("Ошибка создания URI");
            e.printStackTrace();
        }
    }
}
```

## Expirience

1. _TR-Soft August 2023 - now_
2. _Startup July 2023 - September 2023_
3. _Freelance 2022 - 2023_

## Education

_St-Petersburg State University of Architecture and Civil Engineering 2010-2015_

## Languages

- _Russian - native_
- _English - B2_
