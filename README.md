<div class="clearfix announce instapaper_body md" id="readme">
    <span class="name">
      <span class="octicon octicon-book"></span>
      README.md
    </span>

    <article itemprop="mainContentOfPage" class="markdown-body entry-content"><h1>
<a href="#bootstrap-for-sass" class="anchor" name="bootstrap-for-sass"><span class="octicon octicon-link"></span></a>Bootstrap for Sass</h1>

<p><a href="http://travis-ci.org/twbs/bootstrap-sass"><img style="max-width:100%;" alt="Build Status" src="https://secure.travis-ci.org/twbs/bootstrap-sass.png?branch=master"></a></p>

<p><code>bootstrap-sass</code> is a Sass-powered version of <a href="http://github.com/twbs/bootstrap">Bootstrap</a>, ready to drop right into your Sass powered applications.</p>

<h2>
<a href="#installation" class="anchor" name="installation"><span class="octicon octicon-link"></span></a>Installation</h2>

<p>Please see the appropriate guide for your environment of choice:</p>

<h3>
<a href="#a-rails" class="anchor" name="a-rails"><span class="octicon octicon-link"></span></a>a. Rails</h3>

<p><code>bootstrap-sass</code> is easy to drop into Rails with the asset pipeline.</p>

<p>In your Gemfile you need to add the <code>bootstrap-sass</code> gem, and ensure that the <code>sass-rails</code> gem is present - it is added to new Rails applications by default.</p>

<div class="highlight highlight-ruby"><pre><span class="n">gem</span> <span class="s1">'sass-rails'</span><span class="p">,</span> <span class="s1">'&gt;= 3.2'</span> <span class="c1"># sass-rails needs to be higher than 3.2</span>
<span class="n">gem</span> <span class="s1">'bootstrap-sass'</span><span class="p">,</span> <span class="s1">'~&gt; 3.0.3.0'</span>
</pre></div>

<p><code>bundle install</code> and restart your server to make the files available through the pipeline.</p>

<h3>
<a href="#b-compass-no-rails" class="anchor" name="b-compass-no-rails"><span class="octicon octicon-link"></span></a>b. Compass (no Rails)</h3>

<p>Install the gem</p>

<div class="highlight highlight-sh"><pre>gem install bootstrap-sass
</pre></div>

<p>If you have an existing Compass project:</p>

<div class="highlight highlight-ruby"><pre><span class="c1"># config.rb:</span>
<span class="nb">require</span> <span class="s1">'bootstrap-sass'</span>
</pre></div>

<div class="highlight highlight-console"><pre><span class="go">bundle exec compass install bootstrap</span>
</pre></div>

<p>If you are creating a new Compass project, you can generate it with bootstrap-sass support:</p>

<div class="highlight highlight-console"><pre><span class="go">bundle exec compass create my-new-project -r bootstrap-sass --using bootstrap</span>
</pre></div>

<p>This will create a new Compass project with the following files in it:</p>

<ul>
<li>
<a href="/twbs/bootstrap-sass/blob/master/templates/project/_variables.scss.erb">_variables.scss</a> - all of bootstrap variables (override them here).</li>
<li>
<a href="/twbs/bootstrap-sass/blob/master/templates/project/styles.scss">styles.scss</a> - main project SCSS file, import <code>variables</code> and <code>bootstrap</code>.</li>
</ul><h3>
<a href="#c-sass-only-no-compass-nor-rails" class="anchor" name="c-sass-only-no-compass-nor-rails"><span class="octicon octicon-link"></span></a>c. Sass-only (no Compass, nor Rails)</h3>

<p>Require the gem, and load paths and Sass helpers will be configured automatically:</p>

<div class="highlight highlight-ruby"><pre><span class="nb">require</span> <span class="s1">'bootstrap-sass'</span>
</pre></div>

<p>Using bootstrap-sass as a Bower package is still being tested. You can install it with:</p>

<div class="highlight highlight-bash"><pre>bower install <span class="s1">'git://github.com/twbs/bootstrap-sass.git#v3.0.3-0'</span>
</pre></div>

<h4>
<a href="#js-and-fonts" class="anchor" name="js-and-fonts"><span class="octicon octicon-link"></span></a>JS and fonts</h4>

<p>If you are using Rails or Sprockets, see Usage.</p>

<p>If none of Rails/Sprockets/Compass were detected the fonts will be referenced as:</p>

<div class="highlight highlight-sass"><pre><span class="s2">"</span><span class="si">#{</span><span class="nv">$icon-font-path</span><span class="si">}</span><span class="s2">/</span><span class="si">#{</span><span class="nv">$icon-font-name</span><span class="si">}</span><span class="s2">.eot"</span>
</pre></div>

<p><code>$icon-font-path</code> defaults to <code>bootstrap/</code>.</p>

<p>When not using an asset pipeline, you have to copy fonts and javascripts from the gem.</p>

<div class="highlight highlight-bash"><pre>mkdir public/fonts
cp -r <span class="k">$(</span>bundle show bootstrap-sass<span class="k">)</span>/vendor/assets/fonts/ public/fonts/
mkdir public/javascripts
cp -r <span class="k">$(</span>bundle show bootstrap-sass<span class="k">)</span>/vendor/assets/javascripts/ public/javascripts/
</pre></div>

<p>In ruby you can get the assets' location in the filesystem like this:</p>

<div class="highlight highlight-ruby"><pre><span class="no">Bootstrap</span><span class="o">.</span><span class="n">stylesheets_path</span>
<span class="no">Bootstrap</span><span class="o">.</span><span class="n">fonts_path</span>
<span class="no">Bootstrap</span><span class="o">.</span><span class="n">javascripts_path</span>
</pre></div>

<h2>
<a href="#usage" class="anchor" name="usage"><span class="octicon octicon-link"></span></a>Usage</h2>

<h3>
<a href="#sass" class="anchor" name="sass"><span class="octicon octicon-link"></span></a>Sass</h3>

<p>Import Bootstrap into a Sass file (for example, <code>application.css.scss</code>) to get all of Bootstrap's styles, mixins and variables!
We recommend against using <code>//= require</code> directives, since none of your other stylesheets will be <a href="https://github.com/twbs/bootstrap-sass/issues/79#issuecomment-4428595">able to access</a> the Bootstrap mixins or variables.</p>

<div class="highlight highlight-scss"><pre><span class="k">@import</span> <span class="s2">"bootstrap"</span><span class="p">;</span>
</pre></div>

<p>You can also include optional bootstrap theme:</p>

<div class="highlight highlight-scss"><pre><span class="k">@import</span> <span class="s2">"bootstrap/theme"</span><span class="p">;</span>
</pre></div>

<p>The full list of bootstrap variables can be found <a href="http://getbootstrap.com/customize/#less-variables">here</a>. You can override these by simply redefining the variable before the <code>@import</code> directive, e.g.:</p>

<div class="highlight highlight-scss"><pre><span class="nv">$navbar-default-bg</span><span class="o">:</span> <span class="mh">#312312</span><span class="p">;</span>
<span class="nv">$light-orange</span><span class="o">:</span> <span class="mh">#ff8c00</span><span class="p">;</span>
<span class="nv">$navbar-default-color</span><span class="o">:</span> <span class="nv">$light-orange</span><span class="p">;</span>

<span class="k">@import</span> <span class="s2">"bootstrap"</span><span class="p">;</span>
</pre></div>

<p>You can also import components explicitly. To start with a full list of modules copy this file from the gem:</p>

<div class="highlight highlight-bash"><pre><span class="c"># copy and prepend "bootstrap/" to the @import paths:</span>
sed <span class="s1">'s/@import "/@import "bootstrap\//'</span> <span class="se">\</span>
 <span class="k">$(</span>bundle show bootstrap-sass<span class="k">)</span>/vendor/assets/stylesheets/bootstrap/bootstrap.scss &gt; <span class="se">\</span>
 app/assets/stylesheets/bootstrap-custom.scss
</pre></div>

<p>Comment out components you do not want from <code>bootstrap-custom</code>.</p>

<p>In <code>application.sass</code>, replace <code>@import 'bootstrap'</code> with:</p>

<div class="highlight highlight-scss"><pre>  <span class="k">@import</span> <span class="s1">'</span><span class="s2">bootstrap-custom'</span><span class="p">;</span>
</pre></div>

<h3>
<a href="#javascript" class="anchor" name="javascript"><span class="octicon octicon-link"></span></a>Javascript</h3>

<p>We have a helper that includes all Bootstrap javascripts. If you use Rails (or Sprockets separately),
put this in your Javascript manifest (usually in <code>application.js</code>) to load the files in the <a href="/twbs/bootstrap-sass/blob/master/vendor/assets/javascripts/bootstrap.js">correct order</a>:</p>

<div class="highlight highlight-js"><pre><span class="c1">// Loads all Bootstrap javascripts</span>
<span class="c1">//= require bootstrap</span>
</pre></div>

<p>You can also load individual modules, provided you also require any dependencies. You can check dependencies in the <a href="http://getbootstrap.com/javascript/#transitions">Bootstrap JS documentation</a>.</p>

<div class="highlight highlight-js"><pre><span class="c1">//= require bootstrap/scrollspy</span>
<span class="c1">//= require bootstrap/modal</span>
<span class="c1">//= require bootstrap/dropdown</span>
</pre></div>

<hr><h2>
<a href="#development-and-contributing" class="anchor" name="development-and-contributing"><span class="octicon octicon-link"></span></a>Development and Contributing</h2>

<p>If you'd like to help with the development of bootstrap-sass itself, read this section.</p>

<h3>
<a href="#upstream-converter" class="anchor" name="upstream-converter"><span class="octicon octicon-link"></span></a>Upstream Converter</h3>

<p>Keeping bootstrap-sass in sync with upstream changes from Bootstrap used to be an error prone and time consuming manual process. With Bootstrap 3 we have introduced a converter that automates this.</p>

<p><strong>Note: if you're just looking to <em>use</em> Bootstrap 3, see the <a href="#installation">installation</a> section above.</strong></p>

<p>Upstream changes to the Bootstrap project can now be pulled in using the <code>convert</code> rake task.</p>

<p>Here's an example run that would pull down the master branch from the main <a href="https://github.com/twbs/bootstrap">twbs/bootstrap</a> repo:</p>

<pre><code>rake convert
</code></pre>

<p>This will convert the latest LESS to SASS and update to the latest JS.
To convert a specific branch or version, pass the branch name or the commit hash as the first task argument:</p>

<pre><code>rake convert[e8a1df5f060bf7e6631554648e0abde150aedbe4]
</code></pre>

<p>The latest converter script is located <a href="https://github.com/twbs/bootstrap-sass/blob/3/tasks/converter.rb">here</a> and does the following:</p>

<ul>
<li>Converts upstream bootstrap LESS files to its matching SCSS file.</li>
<li>Copies all upstream JavaScript into <code>vendor/assets/javascripts/bootstrap</code>
</li>
<li>Generates a javascript manifest at <code>vendor/assets/javascripts/bootstrap.js</code>
</li>
<li>Copies all upstream font files into <code>vendor/assets/fonts/bootstrap</code>
</li>
<li>Sets <code>Bootstrap::BOOTSTRAP_SHA</code> in <a href="https://github.com/twbs/bootstrap-sass/blob/3/lib/bootstrap-sass/version.rb">version.rb</a> to the branch sha.</li>
</ul><p>This converter fully converts original LESS to SCSS. Conversion is automatic but requires instructions for certain transformations (see converter output).
Please submit GitHub issues tagged with <code>conversion</code>.</p>

<h2>
<a href="#credits" class="anchor" name="credits"><span class="octicon octicon-link"></span></a>Credits</h2>

<p>bootstrap-sass has a number of major contributors:</p>



<ul>
<li><a href="https://twitter.com/thomasmcdonald_">Thomas McDonald</a></li>
<li><a href="http://www.trisweb.com">Tristan Harward</a></li>
<li>Peter Gumeson</li>
<li><a href="https://github.com/glebm">Gleb Mazovetskiy</a></li>
</ul><p>and a <a href="https://github.com/twbs/bootstrap-sass/graphs/contributors">significant number of other contributors</a>.</p>

<h2>
<a href="#youre-in-good-company" class="anchor" name="youre-in-good-company"><span class="octicon octicon-link"></span></a>You're in good company</h2>

<p>bootstrap-sass is used to build some awesome projects all over the web, including
<a href="http://diasporaproject.org/">Diaspora</a>, <a href="https://github.com/sferik/rails_admin">rails_admin</a>,
Michael Hartl's <a href="http://railstutorial.org/">Rails Tutorial</a>, <a href="http://gitlabhq.com/">gitlabhq</a> and
<a href="http://kandanapp.com/">kandan</a>.</p></article>
  </div>