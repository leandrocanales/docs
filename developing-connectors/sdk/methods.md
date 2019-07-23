# Methods

Not all ruby public instance methods are available. Methods are whitelisted to ensure security. The Workato SDK Framework also exposes some methods to make building SDKs convenient.

## REST verb methods

These methods are synonymous to HTTP verbs (GET, POST, PUT, PATCH AND DELETE). These methods are provide you with a very easy way to build and execute HTTP requests without having to think about other details like timeouts, HTTP connection, streaming etc.

Learn how to make HTTP requests using the HTTP verb methods [here](/developing-connectors/sdk/request.md).

## Ruby methods

<table class="unchanged rich-diff-level-one">
  <thead>
    <tr>
      <th>Method</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>at</td>
      <td>Creates a new time object with the given argument. <br>
      <a href="https://apidock.com/ruby/Time/at/class">More details here.</a>  
      </td>
    </tr>
    <tr>
      <td>compact</td>
      <td>Returns a hash with non nil values. <br>
      <a href="https://apidock.com/rails/Hash/compact">More details here.</a>  
      </td>
    </tr>
    <tr>
      <td>dig</td>
      <td>Retrieves the value object corresponding to the index passed in <br>
      The dig method is often used to strip away layers in nested arrays/hashes. For example, we use the dig method often when dealing with XML data formats. <br>
     <a href="https://docs.workato.com/developing-connectors/sdk/data-format/XML-format.html">More details here.</a></td>
    </tr>
    <tr>
      <td>each</td>
      <td>Basic iterator<br><code>[1, 2, 3].each { |i| puts i }</code></td>
    </tr>
    <tr>
      <td>each_with_index</td>
      <td>Iterator returned with an index<br><code>[1, 2, 3].each_with_index { |item, index| puts "#{index}:#{item}" }</code><br> <a href="https://apidock.com/ruby/Enumerator/each_with_index">More details here.</a></td>
    </tr>
    <tr>
      <td>each_with_object</td>
      <td>Iterator returned with an object which you can define
        <code><pre>[%w(foo bar).each_with_object({}) { |str, hsh| hsh[str] = str.upcase }
# => {'foo' => 'FOO', 'bar' => 'BAR'}</pre></code><a href="https://apidock.com/rails/Enumerable/each_with_object">More details here.</a></td>
    </tr>
    <tr>
      <td>even?</td>
      <td>Returns true if integer is an even number<br> <a href="https://apidock.com/ruby/Integer/even%3F">More details here.</a></td>
    </tr>
    <tr>
      <td>fetch</td>
      <td>Returns a value from the hash for the given key.<br> <a href="https://apidock.com/ruby/Hash/fetch">More details here.</a></td>
    </tr>
    <tr>
      <td>format_json</td>
    <td>
        Convert request to json format and expect response body in json format
    </td>
    </tr>
    <tr>
      <td>format_xml</td>
    <td>
        Convert request to XML format and expect response body in XML format
    </td>
    </tr>
    <tr>
      <td>group_by</td>
      <td>
        Group arrays into sets.<br>
        <a href="http://apidock.com/rails/Enumerable/group_by">More details here.</a>
      </td>
    </tr>
     <tr>
      <td>has_key?</td>
      <td>Returns true if the given key is present in hash.<br> <a href="https://apidock.com/ruby/v1_9_3_392/Hash/has_key">More details here.</a></td>
    </tr>
    <tr>
      <td>headers</td>
      <td>
        Add headers to a request<br>
        <code>.headers(Authorization: "Bearer HTB674HJK1")</code>
      </td>
    </tr>
    <tr>
      <td>params</td>
      <td>
        Add parameter to a request<br>
        <code>.params(api_key: "HTB674HJK1")</code>
      </td>
    </tr>
    <tr>
      <td>payload</td>
      <td>
        Add payload to a request<br>
        <code>.payload(id: "345")</code>
      </td>
    </tr>
     <tr>
      <td>pop</td>
      <td>
        Removes the last element from self and returns it, or nil if the array is empty.<br>
        If a number n is given, returns an array of the last n elements (or less) and removes it from array.
        <code><pre>a = [ "a", "b", "c", "d" ]
a.pop     #=> "d"
a.pop(2)  #=> ["b", "c"]
a         #=> ["a"]</pre></code>
        <a href="https://apidock.com/ruby/Array/pop">More details here.</a></td>
      </td>
    </tr>
    <tr>
      <td>ignored</td>
      <td>
        Ignore a comma-separate list of fields<br>
        <code>object_definition["user"].ignored("id", "created_at")</code>
      </td>
    </tr>
    <tr>
      <td>inject</td>
      <td>Combines all elements of enum by applying a binary operation<br> <a href="https://apidock.com/ruby/Enumerable/inject">More details here.</a></td>
    </tr>
    <tr>
      <td>is_a?</td>
      <td>Returns true if class is the class of obj, or if class is one of the superclasses of obj or modules included in obj.<br> Workato currently supports the following classes - Array, Hash, Time, String, Integer, Float <br>
      <a href="https://apidock.com/ruby/Object/is_a%3F">More details here.</a></td>
    </tr>
    <tr>
      <td>iso8601</td>
      <td>This method is equivalent to strftime(‘%F’).<br> <a href="https://apidock.com/ruby/Date/iso8601">More details here.</a></td>
      </tr>
    <tr>
      <td>map</td>
      <td>Returns a new array with the results of running block once for every element in enum.<br> <a href="https://apidock.com/ruby/Enumerable/map">More details here.</a></td>
    </tr>
    <tr>
      <td>merge</td>
      <td>Merges two hashes<br> <a href="https://apidock.com/ruby/Hash/merge">More details here.</a></td>
      </tr>
    <tr>
      <td>odd?</td>
      <td>Returns true if integer is an odd number<br> <a href="https://apidock.com/ruby/Integer/odd%3F">More details here.</a></td>
    </tr>
    <tr>
      <td>only</td>
      <td>
        White list a comma-separate  of fields<br>
        <code>object_definition["user"].only("id", "name")</code>
      </td>
    </tr>
    <tr>
      <td>parse_json</td>
      <td>
        Works the same way as json.parse <br>
        <a href="https://apidock.com/ruby/v1_9_3_392/JSON/parse">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>pluralize</td>
      <td>
        Returns the plural form of the word in the string <br>
        <a href="https://apidock.com/rails/String/pluralize">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>puts</td>
      <td>ruby version of <code>console.log</code> or <code>stdout</code>, not the same as <b>put</b> method</td>
    </tr>
    <tr>
      <td>request_format_json</td>
    <td>
        Convert request to json format
    </td>
    </tr>
    <tr>
      <td>request_format_multipart_form</td>
    <td>
        Convert request to multipart_form format
    </td>
    </tr>
    <tr>
      <td>request_format_www_form_urlencoded</td>
    <td>
        Convert request to url-encoded format
    </td>
    </tr>
    <tr>
      <td>request_format_xml</td>
    <td>
        Convert request to XML format
    </td>
    </tr>
    <tr>
      <td>required</td>
      <td>
        Make a comma-separate list of fields required<br>
        <code>object_definition["user"].required("id", "created_at")</code>
      </td>
    </tr>
    <tr>
      <td>response_format_json</td>
      <td>
        Expect response in json format
      </td>
    </tr>
    <tr>
      <td>response_format_raw</td>
      <td>
        Expect response in raw format
      </td>
    </tr>
    <tr>
      <td>response_format_xml</td>
      <td>
        Expect response in XML format
      </td>
    </tr>
    <tr>
      <td>inject</td>
      <td>
        Combine elements in an array using an operation.<br>
        <a href="http://apidock.com/ruby/Enumerable/inject">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>iso8601</td>
      <td>Convert a date/date-time variable to ISO8601 format</td>
    </tr>
    <tr>
      <td>is_true?</td>
      <td>Converts a value to boolean and returns true if value is truthy.</td>
    </tr>
    <tr>
      <td>is_not_true?</td>
      <td>Converts a value to boolean and returns true if value is not truthy.</td>
    </tr>
    <tr>
      <td>map</td>
      <td>Returns a new array after invoking block on each element</td>
    </tr>
    <tr>
      <td>merge</td>
      <td>
        Returns a new hash containing merged contents.<br>
        <a href="https://ruby-doc.org/core-2.2.0/Hash.html#method-i-merge">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>next</td>
      <td>
        Returns the next object in the enumerator, and move the internal position forward.<br>
        This is often used in config_fields where you can use <code>next</code> as a way to add a guard clause that checks inputs before the lambda function is executed.
        <pre><code style="display: block; white-space: pre-wrap;">object_definition: {
  document: {
    fields: lambda do |connection, config_fields|
      next [] if config_fields.blank?
      get("https://www.webmerge.me/api/documents/#{config_fields["document_id"]}/fields").
        map { |field| field.slice("name") }
    end
  }
}</code></pre>
        <a href="https://apidock.com/ruby/Enumerator/next">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>pluck</td>
      <td>
        Select one or more attributes from an array of objects<br>
        <pre><code style="display: block; white-space: pre-wrap;">[
  {"id": 1, "name": "David"},
  {"id": 2, "name": "Peter"}
].pluck("id")</code></pre>
        returns <code>[1, 2]</code>
      </td>
    </tr>
    <tr>
      <td>rand</td>
      <td>Random number between 0 and 1</td>
    </tr>
    <tr>
      <td>select</td>
      <td>
        Selectively returns elements for which the block returns true.<br>
        <a href="http://apidock.com/ruby/v1_9_3_392/Array/select">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>error</td>
      <td>
        raise a job error with a user-defined error body.<br>
        <code>error("Unable to find Account with ID: 123")</code></a>
      </td>
    </tr>
    <tr>
      <td>reject</td>
      <td>
        Selectively returns elements for which the block returns false. Similar but opposite of <b>select</b>.<br>
        <a href="http://apidock.com/ruby/v1_9_3_392/Array/reject">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>sort</td>
      <td>
        Sort function returning new sorted array.<br>
        <a href="http://apidock.com/ruby/v1_9_3_392/Array/sort">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>sort_by</td>
      <td>
        Sort function returning self.<br>
        <a href="http://apidock.com/ruby/v1_9_3_392/Array/sort_by">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>tap</td>
      <td>
        Yields x to the block, and then returns x.<br>
        The tap method is often used for transformation. For example, we use the tap method below to transform a webhook's payload. If a webhook payload is deliever in this format.
        <pre><code style="display: block; white-space: pre-wrap;">{
  "id" => {"value" => 1},
  "name" => {"value" => 2}
}</code></pre>
        You can use tap to transform it into a more user friendly JSON.<br>
        <pre><code style="display: block; white-space: pre-wrap;">webhook_notification: lambda do |input, payload|
  payload.tap do |output|
    output.each { |k, v| output[k] = v["value"] }
  end
end</code></pre>
      The final JSON will look like this <code>{"id"=>1, "name"=>2}</code><br>
      <a href="https://apidock.com/ruby/Object/tap">More details here.</a></td>
    </tr>
    <tr>
      <td>utc</td>
      <td>
        Convert Time to UTC timezone.<br>
        <a href="http://ruby-doc.org/core-2.2.0/Time.html#method-c-utc">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>while</td>
      <td>
        while loop statement.<br>
        <a href="https://www.tutorialspoint.com/ruby/ruby_loops.htm">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>with_index</td>
      <td>
        Iterates the given block for each element with an index <br>
        <a href="https://apidock.com/ruby/Enumerator/with_index">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>wrap</td>
      <td>
        Wraps its argument in an array unless it is already an array <br> The wrap method is often used in the execute block.
        <pre><code>execute: lambda do |connection, input|
  {
    accounts: Array.wrap(get("/accounts", input)["records"])
  }
end</code></pre>
        This ensures that the <code>accounts</code> variable is always an array in spite of whatever return. At Workato, we often use this to guard against unexpected returns from the various APIs we work with.
        <br>
        <a href="https://apidock.com/rails/Array/wrap/class">More details here.</a>
      </td>
    </tr>
    <tr>
      <td>zip</td>
      <td>Used as a method called by arrays. Converts any arguments to arrays, then merges elements of self with corresponding elements from each argument. <br>
      <a href="https://apidock.com/ruby/Array/zip">More details here.</a>
      </td>
    </tr>
  </tbody>
</table>

This list can and will be expanded constantly, feel free to [contact us](mailto:developer@workato.com) to update/add to this list.

Workato also supports custom reusable methods. See [Reusable Methods](reusable-methods.md) for more information.
