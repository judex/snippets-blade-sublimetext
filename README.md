
<article itemprop="mainContentOfPage" class="markdown-body entry-content">
 <h1>Snippets Blade Sublimetex2</h1>

<p>snippets para <b>Blade</b> en sublimetext es muy simple; nos ahorrar mucho tiempo en escribir, esto fue una necesida que tenia al tener q ahorrame tiempo en hacer formularios </p>

<h2>
<a href="#installation" class="anchor" name="installation"></a>Instalar</h2>
<p>Para instalar solo es necesario descargar los archivos copiar los snippets y guardar en la carpte de <b>User</b> </p><br>
<p>Preferences <b>-></b> Browse Packages..</p>
<p>ubicar la carpeta <b>User</b> y </p>

<code>
	git clone git@github.com:judex/snippets-blade-sublimetext.git
</code>
<h2>Como usar Snippets ?</h2>
<p>Es muy sencillo de usar solo genera los corchete y escribir texto inicial<code> {..} </code><br>Ejemplo</p>

<code>
	{text} + tabulador espacio
</code>
<br>
<h3>Lista de Snippest simple</h3>
<br>
<p>{form}</p>
<code>
{{ Form::open(array('url' => '/', 'method' => 'post', 'name' => '', 'files' => true )) }}
	...

{{ Form::close() }}
</code>
<br>
<p>{text}</p>
	<code>
		{{ Form::text('#hiden')}}
	</code>
<br>
<p>{pass}</p>
	<code>
		{{ Form::password('#name') }}
	</code>
<br>
<p>{label}</p>
	<code>
		{{ Form::label('#hiden', '#show') }}
	</code>
<br>
<p>{email}</p>
	<code>
		{{ Form::email($name, $value = null, $value = array()) }}
	</code>
<br>
<p>{selectRange}</p>
	<code>
		{{ Form::selectRange('number', 10, 20) }}
	</code>
<br>
<p>{selectMonth}</p>
	<code>
		{{ Form::selectMonth('month') }}
	</code>
<br>
<p>{check}</p>
	<code>
		{{ Form::checkbox('name', 'value' true) }}
	</code>
<br>
<p>{radio}</p>
	<code>
		{{ Form::radio('name', 'value') }}
	</code>
<br>
<p>{pass}</p>

		{ Form::radio('name', 'value') }}

<br>

<p>{file}</p>

		{{ Form::file('name') }}

<br>
<p>{select}</p>


	{{Form::select('animal', array(
    'Cats' => array('leopard' => 'Leopard'),
    'Dogs' => array('spaniel' => 'Spaniel'),))}}


<br>
<p>{sub}</p>


	{{ Form::submit('Enviar') }}



<p>Esbir menos XD</p>

@section('name')
	{{ Form::open(array('url' => '/enviar', 'method' => 'post', 'name' => 'formulario', 'files' => true )) }}
		{{ Form::label('nombre', 'Nombre :') }}
		{{ Form::text('name')}}
		{{ Form::label('apellido', 'Apellidos :') }}
		{{ Form::email($name, $value = null, $attributes = array()) }}
		{{ Form::submit('Enviar') }}
	{{ Form::close() }}
@stop


<p>Bueno espero que les pueda ayudar, a codear menos y para mejorar los snippets puedes contactarte conmigo a mi correo msn.dproyect@gmail.com </p>

</article>
