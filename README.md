- 👋 Hi, I’m Michał
- 👀 I’m interested in ... many different things
- 🌱 I’m currently learning ...
- ✅️ 'Python Object Oriented' with Joe Marini on LinkedInLearning
- ✅️ 'Advanced Python' with Joe Marini on LinkedInLearning
- ✅️ 'Level Up : Python' with Barron Stone on LinkedInLearning (PCAP™ – Certified Associate Python Programmer Level)
- 🔶️ 'Managing Python Projects' with Miki Tebeka on LinkedInLearning
- 🔶️ 'Learning Docker' with Carlos Nunez on LinkedInLearning

```
#!/usr/bin/env python3

my_nick ="SHypoleac"

### Just need an alphabet dict A:1, B:2, Z:26 ##
alphabet_dict = {chr(65 + i): i + 1 for i in range(26)} 

my_nick_in_nmbrs = transform(my_nick,alphabet_dict)

### Step 1 and 2! #
it = sorted(my_nick_in_nmbrs)[:5] + sorted(my_nick_in_nmbrs, reverse=True)[:3] 
### Is there anything left? #
remains = [val for val in my_nick_in_nmbrs if val not in it] 
### Let's put this in the middle! - Step 3! #
it.insert(int(len(it)/2), remains.pop())                          
  
it = transform(it,alphabet_dict)

### print (f"If you can do it without computer, you surely have {it} ;)") #

```
```
> def transform(input_data, cryptodict):
    """Automatically performs encryption or decryption with cryptodict based on the type of input."""
	if isinstance(input_data, str):
		# Encryption mode
		input_data=input_data.upper()
		return [cryptodict[char] if char in cryptodict else ord(char) for char in input_data]
	elif isinstance(input_data, (list, tuple)) and all(isinstance(i, int) for i in input_data):
		# Decryption mode
		inverted_dict = {v: k for k, v in cryptodict.items()}
		return "".join([inverted_dict.get(number, str(number)) for number in input_data])
	else:
		raise ValueError("Input data must be either a string for encryption or a sequence of integers for decryption.")
```



<!---
SHypoleac/SHypoleac is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
