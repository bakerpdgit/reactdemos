<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Matching Drag & Drop Game</title>
    <style>
        body {
            background-color: #e0f7fa;
        }
        #gameArea {
            display: flex;
            justify-content: space-between;
            font-size: 1em;
            font-family: 'Arial', sans-serif;
            border: 2px solid black;
            margin: 20px;
            padding: 20px;
            white-space: pre-line;
        }
        #terms, #definitions {
            display: flex;
            flex-direction: column;
        }
        #terms {
            flex-basis: 25%;
        }
        #definitions {
            flex-basis: 75%;
        }
        .draggable, .droppable {
            height: 80px;
            background-color: white;
            margin: 5px;
            padding: 5px;
            border: 1px solid black;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .draggable {
            cursor: pointer;
        }
        .correct {
            background-color: #a5d6a7; /* Green flash */
        }
        .wrong {
            background-color: #ef9a9a; /* Red flash */
        }
    </style>
</head>
<body>

<h1 style="font-size: 22pt; font-family: 'Arial', sans-serif; text-align: center; font-weight: bold;">Terms Match-Up</h1>

<div id="emoji" style="font-size: 100pt; text-align: center; display: none;">😃</div>

<div id="gameArea">
    <div id="terms"></div>
    <div id="definitions"></div>
</div>

<script>
const originalText = `Character Code:
A binary bit-pattern used to represent a character of text

Character Set
The collection of all characters & their associated bit-pattern codes

ASCII
The standard seven-bit character set for the Latin alphabet, digits & symbols (American Standard Code for Information Interchange)

Pixel:
The smallest element of colour in a bitmap image, normally arranged in a two-dimensional grid. It is short for 'picture element'. If an image's physical size remains constant, then the more pixels there are, the sharper and more detailed the image is.

Bitmap
A matrix of picture elements which make up a digital image composed of tiny blocks of colour (pixels) which are encoded one after the other in binary.

Colour Depth
Refers to the number of bits used to represent the colour of each individual pixel. The more bits used, the greater the number of colours / tones that can be represented.

Image Size
The size as measured by the width x height count of its pixels.

Resolution
Usually given as the number of pixels per inch (ppi). It determines the physical size of an image when it is displayed on screen or printed on paper. A 2000 x 1000 pixel bitmap with a resolution of 200 ppi will measure 10" x 5" when displayed on a screen. The higher the resolution the more detail an image has.

Data Compression
The process of reducing the storage size of files, normally for use online using utility software.

Lossless Compression
Compressing a file in such a way that it can be decompressed without any loss of data to its original state. The file size is not as significantly reduced as with lossy compression.

Lossy Compression
some of the data is permanently removed; the original file cannot be fully restored when the lossy file is decompressed. It can result in a much smaller file size than through lossless compression by removing some of the data.

JPEG
Lossy compression bitmap format most commonly used for storing digital photographs`;

    let audioCtx;
		
	const entries = originalText.split("\n\n").map(entry => {
        const [title, ...definition] = entry.split("\n");
        return { title, definition: definition.join(' ') };
    });

	function setupGame() {
		const termsContainer = document.getElementById('terms');
		const definitionsContainer = document.getElementById('definitions');
		termsContainer.innerHTML = '';
		definitionsContainer.innerHTML = '';

		// Step 1: Create term and definition divs with increasing data-id attributes
		entries.forEach((entry, index) => {
			const termDiv = document.createElement('div');
			termDiv.innerText = entry.title;
			termDiv.classList.add('draggable');
			termDiv.draggable = true;
			termDiv.setAttribute('data-id', index);

			termDiv.addEventListener('dragstart', (e) => {
				e.dataTransfer.setData('text/plain', termDiv.getAttribute('data-id'));
			});

			const definitionDiv = document.createElement('div');
			definitionDiv.innerText = entry.definition;
			definitionDiv.classList.add('droppable');
			definitionDiv.setAttribute('data-id', index);

			definitionDiv.addEventListener('dragover', (e) => {
				e.preventDefault();
			});
			
			// Update the drop event listener to check for game completion
			definitionDiv.addEventListener('drop', (e) => {
				const droppedId = e.dataTransfer.getData('text/plain');
				if (droppedId === definitionDiv.getAttribute('data-id')) {
					definitionDiv.classList.add('correct');
					const termToHide = document.querySelector(`.draggable[data-id="${droppedId}"]`);
					setTimeout(() => {
						termToHide.style.display = 'none';
						definitionDiv.style.display = 'none';
						checkGameComplete(); // Check if the game is complete after a successful match
					}, 500);
				} else {
					definitionDiv.classList.add('wrong');
					setTimeout(() => {
						definitionDiv.classList.remove('wrong');
					}, 500);
				}
			});			

			termsContainer.appendChild(termDiv);
			definitionsContainer.appendChild(definitionDiv);
		});

		// Step 2: Shuffle both sets of divs
		for (const container of [termsContainer, definitionsContainer]) {
			const children = Array.from(container.children);
			while (children.length) {
				const randomIndex = Math.floor(Math.random() * children.length);
				container.appendChild(children.splice(randomIndex, 1)[0]);
			}
		}
	}

	// This function checks if the game is complete
	function checkGameComplete() {
		const remainingTerms = document.querySelectorAll('.draggable:not([style*="display: none"])');
		if (remainingTerms.length === 0) {
			celebrate();
		}
	}

	// This function handles the celebration when the game is complete
	function celebrate() {
		const emoji = document.getElementById('emoji');
		emoji.style.display = 'block';
		let direction = 1;
		let position = 0;

		// Animate the emoji moving up and down
		function animateEmoji() {
			position += direction;
			emoji.style.transform = `translateY(${position}px)`;
			if (position > 10 || position < 0) direction *= -1;
			requestAnimationFrame(animateEmoji);
		}
		animateEmoji();

		// Play the tune
		playTune();
	}

	function playTune() {
		if (!audioCtx) {
			audioCtx = new (window.AudioContext || window.webkitAudioContext)();
		}

		let gainNode = audioCtx.createGain();
		gainNode.gain.setValueAtTime(0.5, audioCtx.currentTime); // set volume to 50%
		gainNode.connect(audioCtx.destination);

		const oscillator = audioCtx.createOscillator();
		oscillator.type = 'square';
		oscillator.connect(gainNode);
		oscillator.start();

		const notes = [300, 300, 350, 350, 400, 400, 450];
		let index = 0;

		function playNote() {
			if (index < notes.length) {
				oscillator.frequency.setValueAtTime(notes[index], audioCtx.currentTime);
				index++;
				setTimeout(playNote, 300);
			} else {
				oscillator.stop();
			}
		}

		playNote();
	}


	if (!audioCtx) {
		audioCtx = new (window.AudioContext || window.webkitAudioContext)();
	}
	setupGame();

</script>
</body>
</html>

