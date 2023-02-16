# Pantheon WP Coding Standards
[![Unofficial Support](https://img.shields.io/badge/pantheon-unsupported-yellow?logo=pantheon&color=FFDC28)](https://pantheon.io/docs/oss-support-levels#unofficial-support) ![Packagist Version](https://img.shields.io/packagist/v/pantheon-systems/pantheon-wp-coding-standards) ![MIT License](https://img.shields.io/github/license/pantheon-systems/Pantheon-WP-Coding-Standards)
PHPCS rulesets for WordPress projects on Pantheon.

This is a work-in-progress...

## Setup
The PHPCS ruleset can be installed via Composer:

`composer require --dev pantheon-systems/pantheon-wp-coding-standards`

## Usage

Run the following command to run the standards checks:

```
vendor/bin/phpcs -s --standard=Pantheon-WP .
```

We recommend using the `-s` flag so that PHPCS will report the specific rule that was violated. This makes it easier to add exclusions or research possible solutions.

## Extending

If you want to customize the defaults or add additional rules, you can create your own standard file (e.g. `phpcs.ruleset.xml`):

```xml
<?xml version="1.0"?>
<ruleset>
	<!-- Files or directories to check -->
	<file>.</file>

	<!-- Include the Pantheon-WP ruleset -->
	<rule ref="Pantheon-WP" />

	<!-- Add additional rules here -->
	<rule ref="WordPress.WP.I18n">
		<properties>
			<property name="text_domain" value="my-plugin" />
		</properties>
</ruleset>
```

You can then reference this file when running PHPCS:

```
vendor/bin/phpcs -s --standard=phpcs.ruleset.xml .
```

## Included Checks

The Pantheon WP standard is based upon [WordPress Coding Standards](https://github.com/WordPress/WordPress-Coding-Standards/), [VIP Coding Standards](https://github.com/Automattic/VIP-Coding-Standards) with some customizations based on [Human Made's Coding Standards](https://github.com/humanmade/coding-standards/).