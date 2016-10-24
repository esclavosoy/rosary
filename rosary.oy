from datetime import date
import os
import time


#This is based on https://github.com/rjbs/misc/blob/master/python/rosary.py


mysteries = { 
	'joyful' : [
		'The Annunciation',
		'The Visitation',
		'The Nativity',
		'The Presentation',
		'The Finding in the Temple'
	],

	'sorrowful' : [
		'The Agony in the Garden',
		'The Scourging at Pillar',
		'The Crowning with Thorns',
		'The Carrying of the Cross',
		'The Crucifixion'
	],

	'glorious' : [
		'The Resurrection of Our Lord',
		'The Ascension of Our Lord',
		'The Descent of the Holy Ghost upon the Apostles',
		'The Assumption of the Blessed Virgin Mary into Heaven',
		'The Coronation of Our Lady as Queen of Heaven and Earth'
	],

	'luminous' : [
		'The Baptism of Jesus',
		'The Wedding of Cana',
		'The Proclamation of the Kingdom of God',
		'The Transfiguration',
		'The institution of the Eucharist'
	]
}


def clear_screen():
	print os.popen("clear").read()

class Rosarist:

	def find_mysterytype(self):
		today = date.weekday(date.today())

		if (today in (0,5)): return 'joyful'
		if (today in (1,4)): return 'sorrowful'
		if (today in (2,6)): return 'glorious'
		if (today == 3):     return 'luminous'

	def find_mystery(self, decade):
		return mysteries[self.mysterytype][decade]

	def say_prayer(self, prayer_name, repetition=None):
		clear_screen()
		print "MysteryType : %s" % (self.mysterytype)
		if (self.mystery): print "Mystery     : %s" % (self.mystery)
		time.sleep(.5)

	def begin_prayer(self):
		self.mysterytype = self.find_mysterytype()
		self.mystery = None

	def pray_rosary(self):
		self.phase = 'Opening'
		self.begin_prayer()
		self.phase = 'Decade'
		for decade in range(5):
			self.mystery = self.find_mystery(decade)
			self.say_prayer('Our Father')
                        raw_input("Press Enter to continue...")
		self.mystery = None
if __name__ == "__main__":
	rosarist = Rosarist()
	rosarist.pray_rosary()
