SolutionCodeMirrorBundle
========================

Integrate the [CodeMirror](http://codemirror.net/) editor in you symfony2 project.

### Install

Just add the following line to your projects composer.json require section, and update vendors:
``` js
"paulferrett/code-mirror-bundle": "dev-master"
```

Enable bundle , add to `AppKernel.php`:
``` php
 new Solution\CodeMirrorBundle\SolutionCodeMirrorBundle()
```
### Configuration
Add default parameters to `config.yml`:
``` yaml
twig:
    form:
        resources:
            - 'SolutionCodeMirrorBundle:Form:code_mirror_widget.html.twig'

assetic:
    bundles:
        - SolutionCodeMirrorBundle

solution_code_mirror:
    parameters:
        mode: text/html
        lineNumbers: true
        lineWrapping: true
        theme: base16-dark
    mode_dirs:
        - @SolutionCodeMirrorBundle/Resources/public/js/mode
    themes_dirs:
        - @SolutionCodeMirrorBundle/Resources/public/css/theme
```


Install assets:
``` bash
$ ./app/console assets:install web --symlink
```

### Usage
``` php
$builder->add('content', 'code_mirror', array(
    'required' => true,
    'parameters' => array(
        'lineNumbers' => true,
        'mode': 'text/html',
        'lineWrapping': true,
        'theme': 'twilight',
    ),
));
```

