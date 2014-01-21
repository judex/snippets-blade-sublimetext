
<article itemprop="mainContentOfPage" class="markdown-body entry-content">
 <h1>Snippets Blade Sublimetex2</h1>

<p>snippets para <b>Blade</b> en sublimetext es muy simple; nos ahorrar mucho tiempo en escribir, esto fue una necesidad que tenia, al tener q ahorrame tiempo en hacer formularios</p>

<h2>
<a href="#installation" class="anchor" name="installation"></a>Instalar</h2>

	git clone git@github.com:judex/snippets-blade-sublimetext.git

<p>Para instalar solo es necesario descargar los archivos y guardar los snippets en la carpte de <b>User</b> </p><br>
<p>Preferences <b>-></b> Browse Packages..</p>
<p>ubicar la carpeta <b>User</b> </p>



<h2>Como usar Snippets ?</h2>
<p>Es muy sencillo de usar solo genera los corchete y escribe dentro el texto inicial<code>{..}</code><br>Ejemplo :</p>

	{tex..} + tabulador espacio

<br>
<h3>Lista de Snippest simples</h3>

<p>{form}</p>



	{{ Form::open(array('url' => '/', 'method' => 'post', 'name' => '', 'files' => true )) }}
		#cod....

	{{ Form::close() }}



<br>
<p>{text}</p>

		{{ Form::text('#hiden')}}

<br>
<p>{pass}</p>

		{{ Form::password('#name') }}

<br>
<p>{label}</p>

		{{ Form::label('#hiden', '#show') }}

<br>
<p>{email}</p>

		{{ Form::email($name, $value = null, $value = array()) }}

<br>
<p>{selectRange}</p>

		{{ Form::selectRange('number', 10, 20) }}

<br>
<p>{selectMonth}</p>

		{{ Form::selectMonth('month') }}

<br>
<p>{check}</p>

		{{ Form::checkbox('name', 'value' true) }}

<br>
<p>{radio}</p>

		{{ Form::radio('name', 'value') }}

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



<p>Escribir menos XD</p>

	{{ Form::open(array('url' => '/enviar', 'method' => 'post', 'name' => 'formulario', 'files' => true )) }}

		{{ Form::label('nombre', 'Nombre :') }}
		{{ Form::text('name')}}
		{{ Form::label('apellido', 'Apellidos :') }}
		{{ Form::email($name, $value = null, $attributes = array()) }}
		{{ Form::submit('Enviar') }}

	{{ Form::close() }}



<p>Bueno espero que les pueda ayudar, a codear menos y para mejorar los snippets puedes contactarte conmigo a mi correo msn.dproyect@gmail.com </p>

</article>
