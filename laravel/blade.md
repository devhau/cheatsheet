# Blade

```php
// Show a section in a template
@yield('name')
@extends('layout.name')
// Begin a section
@section('name')
// End a section
@stop
// End a section and yield
@section('sidebar')
@show
@parent

@include('view.name')
@include('view.name', array('key' => 'value'));
@lang('messages.name')
@choice('messages.name', 1);

@if
@else
@elseif
@endif

@unless
@endunless

@for
@endfor

@foreach
@endforeach

@while
@endwhile

//forelse 4.2 feature
@forelse($users as $user)
@empty
@endforelse

// Echo content
{{ $var }}
// Echo escaped content
{{{ $var }}}
// Echo unescaped content; 5.0 feature
{!! $var !!}
{{-- Blade Comment --}}
// Echoing Data After Checking For Existence
{{{ $name or 'Default' }}}
// Displaying Raw Text With Curly Braces
@{{ This will not be processed by Blade }}
```