# worlddb

This is a copy from 

https://code.google.com/p/worlddb/

I have separated to 3 tables (country, region and city) and i have make some small bug fixes.
It contains 246 countries, 4156 regions and 101.907 cities.

```sql
CREATE TABLE `country` (
  `id` tinyint(3) unsigned NOT NULL AUTO_INCREMENT,
  `iso2` char(2) DEFAULT NULL,
  `name` varchar(64) DEFAULT NULL,
  `geo_lat` double(12,11) DEFAULT NULL,
  `geo_lng` double(12,11) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB  DEFAULT CHARSET=utf8;

CREATE TABLE `region` (
  `id` int(10) unsigned NOT NULL AUTO_INCREMENT,
  `country_id` tinyint(3) unsigned DEFAULT NULL,
  `name` varchar(64) NOT NULL,
  `geo_lat` double(12,11) DEFAULT NULL,
  `geo_lng` double(12,11) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB  DEFAULT CHARSET=utf8;

CREATE TABLE `city` (
  `id` int(10) unsigned NOT NULL AUTO_INCREMENT,
  `country_id` tinyint(3) unsigned NOT NULL,
  `region_id` int(10) unsigned DEFAULT NULL,
  `name` varchar(64) NOT NULL,
  `geo_lat` double(12,11) DEFAULT NULL,
  `geo_lng` double(12,11) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB  DEFAULT CHARSET=utf8;
```

if you find it useful and you improve it or add new data then please don't hesitate to shear it :-)
