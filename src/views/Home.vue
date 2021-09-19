<template>
  <div class="home">
  <button @click="english = !english">switch languages</button>
  <br>
  <textarea :placeholder="message" v-model="text" rows="10"></textarea>
  <p id="output">{{ out }}</p>
  <button class="copy" @click="copytext">copy</button>
  <button v-if="!english && lower" @click="lower = !lower">UPPERCASE</button>
  <button v-if="!english && !lower" @click="lower = !lower">lowercase</button>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  mounted() {
	for (var key in this.translate){
		this.inverted[this.translate[key]] = key;
	}
	console.log(this.inverted)
  },
  data() {
	return {
		english: true,
		lower: true,
		text: '',
		translate: {
			'A': '|',
			'B': '┤',
			'C': '╭',
			'D': '┘',
			'E': '3',
			'F': '╕',
			'G': '╗',
			'H': '╫',
			'I': '┇',
			'J': '╛',
			'K': '╮',
			'L': '╪',
			'M': '┬',
			'N': '╖',
			'O': '┼',
			'P': '╝',
			'Q': '╜',
			'R': '╡',
			'S': '┅',
			'T': '╤',
			'U': '╧',
			'V': '┴',
			'W': '╩',
			'X': '╬',
			'Y': '╣',
			'Z': '╨',
			'1': '⏈',
			'2': '⏆',
			'3': '⏇',
			'4': '⏂',
			'5': '⊕',
			'6': '⏁',
			'7': '⏅',
			'8': '⏃',
			'9': '⏄',
			'0': '⍏',
			' ': '_ '
		},
		inverted: {},
	}
  },
  computed: {
	out() {
		return this.output();
	},
	message(){
		if(this.english)
		return "ent3r text t0 transl@t3";
		else
		return "3╖╤⏇╡ ╤3╬╤ ╤⍏ ╤╡|╖┅╪@╤3";
	}
  },
  methods: {
	output() {
		let out = ''
		let text = this.text.toUpperCase()
		if(this.english){
		for(var i = 0; i < text.length; i++){
			if(!(text.charAt(i) in this.translate)){
				out += text.charAt(i)
			}
			else{
				out += this.translate[text.charAt(i)]
			}
		}
		}else{
		for(var j = 0; j < text.length; j++){
			if(text.charAt(j) == '_') continue;
			if(!(text.charAt(j) in this.inverted)){
				out += text.charAt(j)
			}
			else{
				out += this.inverted[text.charAt(j)]
			}
			
		}
		if (this.lower){
			out = out.toLowerCase()
		}
		}
		return out;
	},
	copytext(){
		let text = this.output()
		navigator.clipboard.writeText(text);
	},
  }

}
</script>
