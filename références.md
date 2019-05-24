# Références de Live Code pour Csound

## Opcodes

**set\_tempo**(itempo)

Règle le tempo sur une valeur `itempo` en beats par minute. 

---

ival = **get\_tempo**()

Retourne le tempo en beats par minute. 

---

**go\_tempo**(inewtempo, incr)

Ajuste le tempo de inewtempo incrémentation positive. 

---

ival = **now**()

Retourne la nouvelle valeur de tempo
(Code utilisé depuis le LivecodeLib.csd de Thorin Kerr's) 

---

ival = **now\_tick**()

Retourne la valeur du tick d'horloge au moment de l'intialisation 

---

ival = **beats**(inumbeats)

Retourne la durée en nombre de beats (noires) 

---

ival = **measures**(inummeasures)

Retourne la durée en nombre de mesures (4 noires)

---

ival = **ticks**(inumbeats)

Retourne la durée en nombre de ticks (doubles croches) 

---

ival = **next\_beat**(ibeatcount)

Retourne le temps à partir de maintenant pour le temps suivant, en arrondissant l'alignement
sur la limite du beat.
(Code utilisé depuis le LivecodeLib.csd de Thorin Kerr's)

---

ival = **next\_measure**()

Retourne le temps de maintenant à la mesure suivante, arrondit à la limite de la mesure. 

---

**reset\_clock**()

Réinitialiser l'horloge pour que le prochain tick commence à 0.

---

**adjust\_clock**(iadjust)

Ajuste l'horloge d'un nombre iadjust de beats.
La valeur doit être positive ou négative. 

---

ival = **choose**(iamount)

Avec une valeur aléatoire comprise entre 0 et 1, calcule une valeur aléatoire et
renvoie 1 si la valeur est inférieure à la valeur du hasard. Par exemple, donnant une valeur de 0,7,
il peut indiquer "70% du temps, renvoyer 1; sinon 0"

---

ival = **cycle**(indx, kvals[])

Parcourt karray en utilisant l’index. 

---

ival = **contains**(ival, iarr[])

Vérifie si l'élément existe dans le tableau. Retourne 1 si
vrai et 0 si faux. 

---

ival = **contains**(ival, karr[])

Vérifie si l'élément existe dans le tableau. Retourne 1 si
vrai et 0 si faux. 

---

k[]val = **remove**(ival, karr[])

Créer un nouveau tableau en supprimant toutes les occurrences d’un
numéro donné à partir d'un tableau existant.

---

ival = **rand**(kvals[])

Retourne une donnée aléatoire depuis karray. 

---

Sval = **rand**(Svals[])

Retourne une donnée aléatoire depuis un tableau String. 

---

kval = **randk**(kvals[])

Retourne une valeur aléatoire depuis karray. 

---

Sval = **randk**(Svals[])

Retourne une valeur aléatoire depuis karray. 

---

**cause**(Sinstr, istart, idur, ifreq, iamp)

Opcode wrapper qui appelle la planification uniquement si iamp> 0. 

---

ival = **hexbeat**(Spat, itick)

Étant donné un modèle de chaîne de temps hexadécimal et facultatif
itick (par défaut, current\_tick()), renvoie la valeur 1 si
le tick donnée correspond à un hit dans le temps hexadécimal, ou
renvoie 0 sinon.

---

**hexplay**(Spat, itick, Sinstr, idur, ifreq, iamp)

Pour un pattern de hex beat, utilise le itick pour un instrument, une durée, une fréquence et
amplitude

---

**hexplay**(Spat, Sinstr, idur, ifreq, iamp)

Pour un pattern de hex beat, utilise l'horloge globale pour un instrument, une durée, une fréquence et
amplitude

---

ival = **octalbeat**(Spat, itick)

Pour un patterne en octal beat et un itick optionnel (par défaut, current\_tick()), renvoie la valeur 1 si
le tick donnée correspond à un hit dans le temps octal, ou
renvoie 0 sinon.

---

**octalplay**(Spat, ibeat, Sinstr, idur, ifreq, iamp)



---

**octalplay**(Spat, Sinstr, idur, ifreq, iamp)



---

ival = **phs**(icount, iperiod)

Pour un compte et une période donné, retourne une valeur dans la plage [0-1)

---

ival = **phs**(iticks)

Pour une période en ticks, retourne la phase de l'horloge dans la plage [0-1) 

---

ival = **phsb**(ibeats)

Pour une période donnée en beats, retourne la phase de l'horloge pour la plage [0-1) 

---

ival = **phsm**(imeasures)

Pour une période donnée en mesures, retourne la phase de l'horloge pour la plage [0-1)

---

Sval = **euclid\_str**(ihits, isteps)



---

ival = **euclid**(ihits, isteps, itick)

Pour un nombre ihits pour la période isteps et un itick optionnel (par défaut, current\_tick()), renvoie la valeur 1 si
le tick donnée correspond à un hit du rythme euclidien, ou
renvoie 0 sinon.

---

**euclidplay**(ihits, isteps, itick, Sinstr, idur, ifreq, iamp)



---

**euclidplay**(ihits, isteps, Sinstr, idur, ifreq, iamp)



---

ival = **xcos**(iphase)

Retourne le cosinus de la phase (0-1.0) 

---

ival = **xcos**(iphase, ioffset, irange)

Range version of xcos, similar à Impromptu's cosr 

---

ival = **xsin**(iphase)

Retourne la sinusoïde de la phase (0-1.0) 

---

ival = **xsin**(iphase, ioffset, irange)

Range version of xsin, similar to Impromptu's sinr 

---

ival = **xosc**(iphase, kvals[])

Non-interpolating oscillateur. Donne une phase dans un intervale 0-1,
retourne une valeur comprise dans la table k-array donnée. 

---

ival = **xosci**(iphase, kvals[])

Linearly-interpolating oscillateur. Donne une phase dans un intervale 0-1,
retourne une valeur d'interpolation entre deux points de phase compris dans la table k-array donnée. 

---

ival = **xlin**(iphase, istart, iend)

Line (Ramp) oscillateur.  Donne une phase dans un intervale 0-1, retourne la valeur d'interpolation comprise entre istart et iend. 

---

Sval = **rotate**(Sval, irot)

rotate - Rotation de la phrase autour d'un nombre irot de valeurs.
(Inspiré de rotate par Charlie Roberts' Gibber.)


---

Sval = **strrep**(Sval, inum)

Repeats a given String x number of times. For example, `Sval = strrep("ab6a", 2)` will produce the value of "ab6aab6a". Useful in working with Hex beat strings.  

---

ival = **xchan**(SchanName, initVal)

xchan
Initializes a channel with initial value if channel has default value of 0 and
then returns the current value from the channel. Useful in live coding to define
a dynamic point that will be automated or set outside of the instrument that is
using the channel.

Opcode is overloaded to return i- or k- value. Be sure to use xchan:i or xchan:k
to specify which value to use.


---

kval = **xchan**(SchanName, initVal)

xchan
Initializes a channel with initial value if channel has default value of 0 and
then returns the current value from the channel. Useful in live coding to define
a dynamic point that will be automated or set outside of the instrument that is
using the channel.

Opcode is overloaded to return i- or k- value. Be sure to use xchan:i or xchan:k
to specify which value to use.


---

**set\_root**(iscale_root)

Set root note of scale in MIDI note number. 

---

ival = **from\_root**(ioct, ipc)

Calculate frequency from root note of scale, using
octave and pitch class. 

---

**set\_scale**(Scale)

Set the global scale.  Currently supports "maj" for major and "min" for minor scales. 

---

ival = **in\_scale**(ioct, idegree)

Calculate frequency from root note of scale, using
octave and scale degree. 

---

kval = **in\_scale**(koct, kdegree)

Calculate frequency from root note of scale, using
octave and scale degree. (k-rate version of opcode) 

---

ival = **pc\_quantize**(ipitch_in, iscale[])

Quantizes given MIDI note number to the given scale
(Base on pc:quantize from Extempore) 

---

ival = **pc\_quantize**(ipitch_in)

Quantizes given MIDI note number to the current active scale
(Base on pc:quantize from Extempore) 

---

**set\_chord**(ichord_root, ichord_intervals[])



---

**set\_chord**(Schord)



---

ival = **in\_chord**(ioct, idegree)



---

aval = **declick**(ain)

Utility opcode for declicking an audio signal. Should only be used in instruments that have positive p3 duration. 

---

kval = **oscil**(kfreq, kin[])

Custom non-interpolating oscil that takes in kfrequency and array to use as oscillator table
data. Outputs k-rate signal. 

---

**kill**(Sinstr)

Turns off running instances of named instruments.  Useful when livecoding
audio and control signal process instruments. May not be effective if for
temporal recursion instruments as they may be non-running but scheduled in the
event system. In those situations, try using clear\_instr to overwrite the
instrument definition. 

---

**clear\_instr**(Sinstr)

Redefines instr to empty body. Useful for killing
temporal recursion or clock callback functions 

---

**start**(Sinstr)

Starts running a named instrument for indefinite time using p2=0 and p3=-1.
Will first turnoff any instances of existing named instrument first.  Useful
when livecoding always-on audio and control signal process instruments. 

---

**stop**(Sinstr)

Stops a running named instrument, allowing for release segments to operate. 

---

**eval\_at\_time**(Scode, istart)

Evaluate code at a given time 

---

**set\_fade\_range**(irange)

Sets the range in db to fade over. By default, range is -30 (i.e., fades from -30dbfs to 0dbfs) 

---

ival = **fade\_in**(ident, inumticks)

Given a fade channel identifier (number) and number of ticks to fade over time, advances from current fade channel value towards 0dbfs (1.0) using the globally set fade range. (By default starts fading in from -30dBfs and stops at 0dbfs.) 

---

ival = **fade\_out**(ident, inumticks)

Given a fade channel identifier (number) and number of ticks to fade over time, advances from current fade channel value towards 0 using the globally set fade range. (By default starts fading out from 0dBfs and stops at -30dbfs.) 

---

ival = **fade\_read**(ident)

Read value from fade channel. Useful if copy/pasting then wanting to just read from fade and control in the original code. 

---

**set\_fade**(ident, ival)

 Set value for fade channel to given value. Should be in range 0-1.0.  (Typically one sets to either 0 or 1.) 

---

**sbus\_write**(ibus, al, ar)

Write two audio signals into stereo bus at given index 

---

**sbus\_mix**(ibus, al, ar)

Mix two audio signals into stereo bus at given index 

---

**sbus\_clear**(ibus)

Clear audio signals from bus channel 

---

aaval = **sbus\_read**(ibus)

Read audio signals from bus channel 

---

**pan\_verb\_mix**(asig, kpan, krvb)

Utility opcode to pan signal, send dry to mixer, and send amount
of signal to reverb. If ReverbMixer is not on, will output just
panned signal using out opcode. 

---

aval = **saturate**(asig, ksat)

Saturation using tanh 

---

## Instruments

|Instrument Name | Description |
| ---- | ---- | 
|  ReverbMixer | Always-on Mixer instrument with Reverb send channel. Use start("ReverbMixer") to run. Designed for use with pan\_verb\_mix to simplify signal-based live coding.  | 
|  Sub1 | Substractive Synth, 3osc  | 
|  Sub2 | Subtractive Synth, two saws, fifth freq apart  | 
|  Sub3 | Subtractive Synth, three detuned saws, swells in  | 
|  Sub4 | Subtractive Synth, detuned square/saw, stabby. Nice as a lead in octave 2, nicely grungy in octave -2, -1  | 
|  Sub5 | Subtractive Synth, detuned square/triangle  | 
|  Sub6 | Subtractive Synth, saw, K35 filters  | 
|  Sub7 | Subtractive Synth, saw + tri, K35 filters  | 
|  SynBrass | SynthBrass subtractive synth  | 
|  SSaw | SuperSaw sound using 9 bandlimited saws (3 sets of detuned saws at octaves) | 
|  Mode1 | Modal Synthesis Instrument: Percussive/organ-y sound  | 
|  Plk | Pluck sound using impulses, noise, and waveguides | 
|  Bass | 303-style Bass sound  | 
|  ms20_bass | MS20-style Bass Sound  | 
|  VoxHumana | VoxHumana Patch  | 
|  FM1 | FM 3:1 C:M ratio, 2->0.025 index, nice for bass  | 
|  Noi | Filtered noise, exponential envelope  | 
|  Wobble | Wobble patched based on Jacob Joaquin's "Tempo-Synced Wobble Bass"  | 
|  Sine | Simple Sinewave instrument with exponential envelope  | 
|  Mono | Monophone synth using sawtooth wave and 4pole lpf. Use "start("Mono") to run the monosynth, then use MonoNote instrument to play the instrument.  | 
|  MonoNote | Note playing instrument for Mono synth. Be careful to use this and not try to create multiple Mono instruments!  | 
|  Clap | Modified clap instrument by Istvan Varga (clap1.orc)  | 
|  BD   | Bass Drum - From Iain McCurdy's TR-808.csd  | 
|  SD   | Snare Drum - From Iain McCurdy's TR-808.csd  | 
|  OHH  | Open High Hat - From Iain McCurdy's TR-808.csd  | 
|  CHH  | Closed High Hat - From Iain McCurdy's TR-808.csd  | 
|  HiTom  | High Tom - From Iain McCurdy's TR-808.csd  | 
|  MidTom  | Mid Tom - From Iain McCurdy's TR-808.csd  | 
|  LowTom   | Low Tom - From Iain McCurdy's TR-808.csd  | 
|  Cymbal   | Cymbal - From Iain McCurdy's TR-808.csd  | 
|  Rimshot  | Rimshot - From Iain McCurdy's TR-808.csd  | 
|  Claves | Claves - From Iain McCurdy's TR-808.csd  | 
|  Cowbell | Cowbell - From Iain McCurdy's TR-808.csd  | 
|  Maraca   | Maraca - from Iain McCurdy's TR-808.csd  | 
|  HiConga  | High Conga - From Iain McCurdy's TR-808.csd  | 
|  MidConga   | Mid Conga - From Iain McCurdy's TR-808.csd  | 
|  LowConga   | Low Conga - From Iain McCurdy's TR-808.csd  | 
