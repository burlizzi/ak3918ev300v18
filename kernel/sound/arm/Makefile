#
# Makefile for ALSA
#

obj-$(CONFIG_SND_ARMAACI)	+= snd-aaci.o
snd-aaci-objs			:= aaci.o

obj-$(CONFIG_SND_PXA2XX_PCM)	+= snd-pxa2xx-pcm.o
snd-pxa2xx-pcm-objs		:= pxa2xx-pcm.o

obj-$(CONFIG_SND_PXA2XX_LIB)	+= snd-pxa2xx-lib.o
snd-pxa2xx-lib-y		:= pxa2xx-pcm-lib.o
snd-pxa2xx-lib-$(CONFIG_SND_PXA2XX_LIB_AC97)	+= pxa2xx-ac97-lib.o

obj-$(CONFIG_SND_PXA2XX_AC97)	+= snd-pxa2xx-ac97.o
snd-pxa2xx-ac97-objs		:= pxa2xx-ac97.o

obj-$(CONFIG_SND_AK_PCM)    += snd-akpcm.o
snd-akpcm-objs               := ak_pcm.o

obj-$(CONFIG_CODEC_AK39)	+= snd-codec-ak39.o
snd-codec-ak39-objs			:= ak39_codec.o

obj-$(CONFIG_CODEC_WM8523)	+= snd-codec-wm8523.o
snd-codec-wm8523-objs			:= wm8523.o
