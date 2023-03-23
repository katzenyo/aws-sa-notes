
- Text translation service (ML based)
- Translates text from native language to other languages
	- Translates one word at a time
- Encoder reads source -> semantic representation (meaning)
- Decoder reads the meaning -> writes into target language
- Attention mechanisms ensure 'meaning' is translated accurately
- Auto detect source text language

## Use Cases

- Multilingual user experiences
	- Meeting notes, posts, communications, articles, etc
	- Emails, in-game chat, customer live chat
- Translate incoming data (social media/news/communications)
- Language-independence for other AWS services
	- Comprehend, transcribe, [[Amazon Polly]], Data stored in S3, RDS, DDB
- Commonly integrates with other AWS services/apps/platforms
	- Not generally used on its own