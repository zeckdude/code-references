## Selectors

#### Various selectors to target elements for manipulation
##### [selectors] (https://api.jquery.com/category/selectors/)
##### [Selector Testing tool] (http://www.w3schools.com/jquery/trysel.asp)

| Selector | Example | Selects |
|---------------|-------|--------|
| [*](http://www.w3schools.com/jquery/sel_all.asp) | `$("*")` | All elements |
| [#_id_](http://www.w3schools.com/jquery/sel_id.asp) | `$("#lastname")` | The element with id="lastname" |
| [._class_](http://www.w3schools.com/jquery/sel_class.asp) | `$(".intro")` | All elements with class="intro" |
| [._class,_._class_](http://www.w3schools.com/jquery/sel_multiple_classes.asp) | `$(".intro,.demo")` | All elements with the class "intro" or "demo" |
| [_element_](http://www.w3schools.com/jquery/sel_element.asp) | `$("p")` | All `<p>` elements |
| [_el1_,_el2_,_el3_](http://www.w3schools.com/jquery/sel_multiple_sel.asp) | `$("h1,div,p")` | All `<h1>`, `<div>` and `<p>` elements |
| [:first](http://www.w3schools.com/jquery/sel_first.asp) | `$("p:first")` | The first `<p>` element |
| [:last](http://www.w3schools.com/jquery/sel_last.asp) | `$("p:last")` | The last `<p>` element |
| [:even](http://www.w3schools.com/jquery/sel_even.asp) | `$("tr:even")` | All even `<tr>` elements |
| [:odd](http://www.w3schools.com/jquery/sel_odd.asp) | `$("tr:odd")` | All odd `<tr>` elements |
| [:first-child](http://www.w3schools.com/jquery/sel_firstchild.asp) | `$("p:first-child")` | All `<p>` elements that are the first child of their parent |
| [:first-of-type](http://www.w3schools.com/jquery/sel_firstoftype.asp) | `$("p:first-of-type")` | All `<p>` elements that are the first `<p>` element of their parent |
| [:last-child](http://www.w3schools.com/jquery/sel_lastchild.asp) | `$("p:last-child")` | All `<p>` elements that are the last child of their parent |
| [:last-of-type](http://www.w3schools.com/jquery/sel_lastoftype.asp) | `$("p:last-of-type")` | All `<p>` elements that are the last `<p>` element of their parent |
| [:nth-child(_n_)](http://www.w3schools.com/jquery/sel_nthchild.asp) | `$("p:nth-child(2)")` | All `<p>` elements that are the 2nd child of their parent |
| [:nth-last-child(_n_)](http://www.w3schools.com/jquery/sel_nthlastchild.asp) | `$("p:nth-last-child(2)")` | All `<p>` elements that are the 2nd child of their parent, counting from the last child |
| [:nth-of-type(_n_)](http://www.w3schools.com/jquery/sel_nthoftype.asp) | `$("p:nth-of-type(2)")` | All `<p>` elements that are the 2nd `<p>` element of their parent |
| [:nth-last-of-type(_n_)](http://www.w3schools.com/jquery/sel_nthlastoftype.asp) | `$("p:nth-last-of-type(2)")` | All `<p>` elements that are the 2nd `<p>` element of their parent, counting from the last child |
| [:only-child](http://www.w3schools.com/jquery/sel_onlychild.asp) | `$("p:only-child")` | All `<p>` elements that are the only child of their parent |
| [:only-of-type](http://www.w3schools.com/jquery/sel_onlyoftype.asp) | `$("p:only-of-type")` | All `<p>` elements that are the only child, of its type, of their parent |
| [parent > child](http://www.w3schools.com/jquery/sel_parent_child.asp) | `$("div > p")` | All `<p>` elements that are a direct child of a `<div>` element |
| [parent descendant](http://www.w3schools.com/jquery/sel_parent_descendant.asp) | `$("div p")` | All `<p>` elements that are descendants of a `<div>` element |
| [element + next](http://www.w3schools.com/jquery/sel_previous_next.asp) | `$("div + p")` | The `<p>` element that are next to each `<div>` elements |
| [element ~ siblings](http://www.w3schools.com/jquery/sel_previous_siblings.asp) | `$("div ~ p")` | All `<p>` elements that are siblings of a `<div>` element |
| [:eq(_index_)](http://www.w3schools.com/jquery/sel_eq.asp) | `$("ul li:eq(3)")` | The fourth element in a list (index starts at 0) |
| [:gt(_no_)](http://www.w3schools.com/jquery/sel_gt.asp) | `$("ul li:gt(3)")` | List elements with an index greater than 3 |
| [:lt(_no_)](http://www.w3schools.com/jquery/sel_lt.asp) | `$("ul li:lt(3)")` | List elements with an index less than 3 |
| [:not(_selector_)](http://www.w3schools.com/jquery/sel_not.asp) | `$("input:not(:empty)")` | All input elements that are not empty |
| [:header](http://www.w3schools.com/jquery/sel_header.asp) | `$(":header")` | All header elements `<h1>`, `<h2>` ... |
| [:animated](http://www.w3schools.com/jquery/sel_animated.asp) | `$(":animated")` | All animated elements |
| [:focus](http://www.w3schools.com/jquery/sel_focus.asp) | `$(":focus")` | The element that currently has focus |
| [:contains(_text_)](http://www.w3schools.com/jquery/sel_contains.asp) | `$(":contains('Hello')")` | All elements which contains the text "Hello" |
| [:has(_selector_)](http://www.w3schools.com/jquery/sel_has.asp) | `$("div:has(p)")` | All `<div>` elements that have a `<p>` element |
| [:empty](http://www.w3schools.com/jquery/sel_empty.asp) | `$(":empty")` | All elements that are empty |
| [:parent](http://www.w3schools.com/jquery/sel_parent.asp) | `$(":parent")` | All elements that are a parent of another element |
| [:hidden](http://www.w3schools.com/jquery/sel_hidden.asp) | `$("p:hidden")` | All hidden `<p>` elements |
| [:visible](http://www.w3schools.com/jquery/sel_visible.asp) | `$("table:visible")` | All visible tables |
| [:root](http://www.w3schools.com/jquery/sel_root.asp) | `$(":root")` | The document's root element |
| [:lang(_language_)](http://www.w3schools.com/jquery/sel_lang.asp) | `$("p:lang(de)")` | All `<p>` elements with a lang attribute value starting with "de" |
| [[_attribute_]](http://www.w3schools.com/jquery/sel_attribute.asp) | `$("[href]")` | All elements with a href attribute |
| [[_attribute_=_value_]](http://www.w3schools.com/jquery/sel_attribute_equal_value.asp) | `$("[href='default.htm']")` | All elements with a href attribute value equal to "default.htm" |
| [[_attribute_!=_value_]](http://www.w3schools.com/jquery/sel_attribute_notequal_value.asp) | `$("[href!='default.htm']")` | All elements with a href attribute value not equal to "default.htm" |
| [[_attribute_$=_value_]](http://www.w3schools.com/jquery/sel_attribute_end_value.asp) | `$("[href$='.jpg']")` | All elements with a href attribute value ending with ".jpg" |
| [[_attribute_&#124;=_value_]](http://www.w3schools.com/jquery/sel_attribute_prefix_value.asp) | `$("[title|='Tomorrow']")` | All elements with a title attribute value equal to 'Tomorrow', or starting with 'Tomorrow' followed by a hyphen |
| [[_attribute_^=_value_]](http://www.w3schools.com/jquery/sel_attribute_beginning_value.asp) | `$("[title^='Tom']")` | All elements with a title attribute value starting with "Tom" |
| [[_attribute_~=_value_]](http://www.w3schools.com/jquery/sel_attribute_contains_value.asp) | `$("[title~='hello']")` | All elements with a title attribute value containing the specific word "hello" |
| [[_attribute*_=_value_]](http://www.w3schools.com/jquery/sel_attribute_contains_string_value.asp) | `$("[title*='hello']")` | All elements with a title attribute value containing the word "hello" |
| [:input](http://www.w3schools.com/jquery/sel_input.asp) | `$(":input")` | All input elements |
| [:text](http://www.w3schools.com/jquery/sel_input_text.asp) | `$(":text")` | All input elements with type="text" |
| [:password](http://www.w3schools.com/jquery/sel_input_password.asp) | `$(":password")` | All input elements with type="password" |
| [:radio](http://www.w3schools.com/jquery/sel_input_radio.asp) | `$(":radio")` | All input elements with type="radio" |
| [:checkbox](http://www.w3schools.com/jquery/sel_input_checkbox.asp) | `$(":checkbox")` | All input elements with type="checkbox" |
| [:submit](http://www.w3schools.com/jquery/sel_input_submit.asp) | `$(":submit")` | All input elements with type="submit" |
| [:reset](http://www.w3schools.com/jquery/sel_input_reset.asp) | `$(":reset")` | All input elements with type="reset" |
| [:button](http://www.w3schools.com/jquery/sel_input_button.asp) | `$(":button")` | All input elements with type="button" |
| [:image](http://www.w3schools.com/jquery/sel_input_image.asp) | `$(":image")` | All input elements with type="image" |
| [:file](http://www.w3schools.com/jquery/sel_input_file.asp) | `$(":file")` | All input elements with type="file" |
| [:enabled](http://www.w3schools.com/jquery/sel_input_enabled.asp) | `$(":enabled")` | All enabled input elements |
| [:disabled](http://www.w3schools.com/jquery/sel_input_disabled.asp) | `$(":disabled")` | All disabled input elements |
| [:selected](http://www.w3schools.com/jquery/sel_input_selected.asp) | `$(":selected")` | All selected input elements |
| [:checked](http://www.w3schools.com/jquery/sel_input_checked.asp) | `$(":checked")` | All checked input elements |

