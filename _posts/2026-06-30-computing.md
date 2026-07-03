---
layout: default
mermaid: true
published: true
image: mermaid.webp
mathjax: true
---



# MathJax : [demo](https://mathjax.github.io/MathJax-demos-web/page/tex-chtml.html)
 [https://mathjax.github.io/MathJax-demos-web/](https://mathjax.github.io/MathJax-demos-web/) 
 @nasa-pds @cityoflosangeles [talk.jekyllrb.com/t/jekyll-and-mathjax-how-to-configure-specific-inline-and-display-math/9551/8](https://talk.jekyllrb.com/t/jekyll-and-mathjax-how-to-configure-specific-inline-and-display-math/9551/8) // [talk.jekyllrb.com/t/jekyll-and-mathjax/5514/2](https://talk.jekyllrb.com/t/jekyll-and-mathjax/5514/2)
 
<p>
  When $a \ne 0$, there are two solutions to \(ax^2 + bx + c = 0\) and they are
  $$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$
</p>

<h2>The Lorenz Equations</h2>

<p>
  \begin{align}
    \dot{x} & = \sigma(y-x) \\
    \dot{y} & = \rho x - y - xz \\
    \dot{z} & = -\beta z + xy
  \end{align}
</p>

<h2>The Cauchy-Schwarz Inequality</h2>

<p>\[
  \left( \sum_{k=1}^n a_k b_k \right)^{\!\!2} \leq
  \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)
 \]</p>

 <h2>A Cross Product Formula</h2>

 <p>\[
   \mathbf{V}_1 \times \mathbf{V}_2 =
     \begin{vmatrix}
       \mathbf{i} & \mathbf{j} & \mathbf{k} \\
       \frac{\partial X}{\partial u} & \frac{\partial Y}{\partial u} & 0 \\
       \frac{\partial X}{\partial v} & \frac{\partial Y}{\partial v} & 0 \\
     \end{vmatrix}
\]</p>

<h2>The probability of getting \(k\) heads when flipping \(n\) coins is:</h2>

<p>\[P(E) = {n \choose k} p^k (1-p)^{ n-k} \]</p>

<h2>An Identity of Ramanujan</h2>

<p>\[
  \frac{1}{\left(\sqrt{\phi \sqrt{5}}-\phi\right) e^{\frac25 \pi}} =
    1 + \dfrac{e^{-2\pi}}{
      1 + \dfrac{e^{-4\pi}}{
        1 + \dfrac{e^{-6\pi}}{
          1 + \dfrac{e^{-8\pi}}{1+\ldots}
        }
      }
    }
\]</p>

<h2>A Rogers-Ramanujan Identity</h2>

<p>\[
  1 + \frac{q^2}{(1-q)}+\frac{q^6}{(1-q)(1-q^2)}+\cdots =
    \prod_{j=0}^{\infty}\frac{1}{(1-q^{5j+2})(1-q^{5j+3})},
     \quad\quad \text{for $|q| < 1$}.
\]</p>

<h2>Maxwell's Equations</h2>

<p>
  \begin{align}
    \nabla \times \vec{\mathbf{B}}\, - \frac{1}{c}\, \frac{\partial\vec{\mathbf{E}}}{\partial t}
       & = \frac{4\pi}{c}\vec{\mathbf{j}} \\[3pt]
    \nabla \cdot \vec{\mathbf{E}} & = 4 \pi \rho \\[3pt]
    \nabla \times \vec{\mathbf{E}}\, + \frac{1}{c}\, \frac{\partial\vec{\mathbf{B}}}{\partial t}
        & = \vec{\mathbf{0}} \\[3pt]
    \nabla \cdot \vec{\mathbf{B}} & = 0
  \end{align}
</p>

<h2>In-line Mathematics</h2>

<p>Finally, while display equations look good for a page of samples, the
ability to mix math and text in a paragraph is also important.  This
expression $\sqrt{3x-1}+(1+x)^2$ is an example of an inline equation.  As
you see, MathJax equations can be used this way as well, without unduly
disturbing the spacing between lines.</p>
## Further reading

* [The MathJax website](http://mathjax.org)
* [Getting started with writing and formatting on GitHub](/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github)
* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)

# Mermaid Sequence Diagram: Blogging app service communication

<div class="mermaid">
sequenceDiagram
    participant web as Web Browser
    participant blog as Blog Service
    participant account as Account Service
    participant mail as Mail Service
    participant db as Storage

    Note over web,db: The user must be logged in to submit blog posts
    web->>+account: Logs in using credentials
    account->>db: Query stored accounts
    db->>account: Respond with query result

    alt Credentials not found
        account->>web: Invalid credentials
    else Credentials found
        account->>-web: Successfully logged in

        Note over web,db: When the user is authenticated, they can now submit new posts
        web->>+blog: Submit new post
        blog->>db: Store post data

        par Notifications
            blog--)mail: Send mail to blog subscribers
            blog--)db: Store in-site notifications
        and Response
            blog-->>-web: Successfully posted
        end
    end

</div>

# Water CoolEr 
<div class="mermaid">
sequenceDiagram
Alice ->> Bob: Hello Bob, how are you?
Bob-->>John: How about you John?
Bob--x Alice: I am good thanks!
Bob-x John: I am good thanks!
Note right of John: Bob thinks a long<br/>long time, so long<br/>that the text does<br/>not fit on a row.
Bob-->Alice: Checking with John...
Alice->John: Yes... John, how are you?
</div> 

# [Server Procurement Takes Too Long: Causes and Effects](https://github.com/rudolfolah/mermaid-diagram-examples/blob/main/diagrams/cause-and-effect.md)
<div class="mermaid">
mindmap
root{{Server Procurement Takes Too Long}}
  (Material)
    not sure what hardware requirements to use as a baseline
    obsolete hardware specifications
    high demand for specific hardware components
  (Vendors)
    convoluted, slow billing process
    limited vendor options
    long lead times for hardware delivery
    inconsistent communication from vendors
  (People)
    too many approvals required
    unclear when costs for server are passed to client
    client is unwilling to procure server
      budget unavailable until milestone is met
      does not see the need for the server
      already has on premises servers
      client does not want to use public cloud infrastructure
    lack of dedicated procurement personnel
    miscommunication between teams
  (Systems)
    procurement is not automated
    outdated procurement software
    lack of integration between procurement and project management tools
    manual tracking of procurement status
</div>

# Class Diagram 

<div class="mermaid">
---
title: Django Watson Class Diagram
---
classDiagram
class SearchAdapter {
  fields
  exclude
  store
  __init__(model)
  prepare_content(content)
  get_title(obj)
  get_description(obj)
  get_content(obj)
  get_url(obj)
  get_meta(obj)
  serialize_meta(obj)
  deserialize_meta(obj)
  get_live_queryset()
}

class SearchContextManager {
  _stack
  __init__()
  is_active()
  start()
  add_to_context(engine, obj)
  invalidate()
  is_invalid()
  end()
  update_index()
  skip_index_update()
}

class SearchContext {
  __init__(context_manager)
  __enter__()
  __exit__(exc_type, exc_value, traceback)
  __call__(func)
}

class SkipSearchContext {
  __exit__(exc_type, exc_value, traceback)
}

class SearchEngine {
  list _created_engines$
  dict _registered_models
  str _engine_slug
  SearchContextManager _search_context_manager
  get_created_engines()$ list
  __init__(engine_slug, search_context_manager)
  is_registered(model) bool
  register(model, adapter_cls, **field_overrides)
  unregister(model)
  get_registered_models() list
  get_adapter(model) SearchAdapter
  cleanup_model_index(model)
  update_obj_index(obj)
  _post_save_receiver(instance, **kwargs)
  _pre_delete_receiver(instance, **kwargs)
  _create_model_filter(models, backend) list
  _get_included_models(models) iter
  search(search_text, models, exclude, ranking, backend_name) Queryset
  filter(queryset, search_text, ranking, backend_name) Queryset
}

Exception <|-- SearchAdapterError
Exception <|-- SearchEngineError
Exception <|-- SearchContextError
SearchEngineError <|-- RegistrationError
SearchContextManager *-- SearchContext
SearchContext <|-- SkipSearchContext

</div>


[codepen.io/ricoThaka/pen/GgRdwGd](https://codepen.io/ricoThaka/pen/GgRdwGd)
<img alt="image" src="https://github.com/user-attachments/assets/7ee591aa-18be-4bd6-ad98-365d0d08c814" />
