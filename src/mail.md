---
title: Orchestra Mail Class
---

* [Force Direct Sending](#force-direct-sending)
* [Force Sending via Queue](#force-send-queue)
* [Sending via Configuration](#sending-via-config)

`Orchestra\Mail` offer a slight improvement to `Illuminate\Mail\Mailer` where administrator can define the e-mail configuration from Settings page as well as preference to use `send` or `queue`.

## Force Direct Sending {#force-direct-sending}

`Orchestra\Mail::send()` deliver what you would expect from `Mail::send()` using the E-mail configuration setup in the Settings Page.

	Orchestra\Mail::send('email.update', $data, function ($m) use ($user) {
		$m->to($user->email);
	});

## Force Sending via Queue {#force-send-queue}

`Orchestra\Mail::queue()` deliver what you would expect from `Mail::queue()` using the E-mail configuration setup in the Settings Page.

	Orchestra\Mail::queue('email.update', $data, function ($m) use ($user) {
		$m->to($user->email);
	});

## Sending via Configuration {#sending-via-config}

`Orchestra\Mail::push()` would first check whether the administrator has choosen to send email directly or delayed it via queue.

	Orchestra\Mail::push('email.update', $data, function ($m) use ($user) {
		$m->to($user->email);
	});

> The API is identical to `Illuminate\Mail\Mailer` with the exception that administrator can configure to choose "Mail via Queue" in the Settings Page.

