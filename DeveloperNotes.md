# Notes to Developers #

  * All unsigned ints of type "u\_intN" have been converted to "uintN" to be consistent throughout the project. This does have an impact on clients using the library, they need to also convert their types to this convention as well.

  * trak.udta.name.metadata has been deprecated in favour of trak.udta.name.value for specifying iTunes audio track names.