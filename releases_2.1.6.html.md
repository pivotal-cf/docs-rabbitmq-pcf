## <a id="2-1-6"></a> v2.1.6

**Release Date**: January 18, 2023

### Resolved Issues

This release fixes the following issues:

* *VE-2022-41720 (Golang issue https://go.dev/issue/56694, fixed in Go 1.19.4)
* CVE-2022-41717 (Golang issue https://go.dev/issue/56350, fixed in Go 1.19.4)
* https://pivotal-io.atlassian.net/browse/RMQFPAS-82 (Fixed by https://github.com/cloudfoundry/loggregator-agent-release/releases/tag/v6.5.6)


### Known Issues

This release has the following known issues:


### Compatibility

The following components are compatible with this release:

<table class="nice"> <th>Component</th> <th>Version</th> 	<tr>
		<td><%= vars.app_runtime_full %></td>
		<td>2.11.x, 2.12.x, 2.13.x</td>
	</tr>
	<tr>
		<td>Erlang</td>
		<td>24.3.4.7, 25.2</td>
	</tr>
	<tr>
		<td>HAProxy</td>
		<td>2.6.7</td>
	</tr>
	<tr>
		<td>OSS RabbitMQ*</td>
		<td>3.9.27</td>
	</tr>
	<tr>
		<td>Stemcell</td>
		<td>621.x</td>
	</tr>
	<tr>
		<td>bpm</td>
		<td>1.1.21</td>
	</tr>
	<tr>
		<td>cf-cli</td>
		<td>1.41.0</td>
	</tr>
	<tr>
		<td>cf-rabbitmq</td>
		<td>478.0.0</td>
	</tr>
	<tr>
		<td>cf-rabbitmq-multitenant-broker</td>
		<td>128.0.0</td>
	</tr>
	<tr>
		<td>cf-rabbitmq-smoke-tests</td>
		<td>154.0.0</td>
	</tr>
	<tr>
		<td>cf-service-gateway</td>
		<td>91.0.0</td>
	</tr>
	<tr>
		<td>loggregator-agent</td>
		<td>7.0.1</td>
	</tr>
	<tr>
		<td>on-demand-service-broker</td>
		<td>0.42.6</td>
	</tr>
	<tr>
		<td>rabbitmq-metrics</td>
		<td>96.0.0</td>
	</tr>
	<tr>
		<td>rabbitmq-on-demand-adapter</td>
		<td>227.0.0</td>
	</tr>
	<tr>
		<td>routing</td>
		<td>0.254.0</td>
	</tr>
	<tr>
		<td>service-metrics</td>
		<td>2.0.24</td>
	</tr>\n</table>

<sup>*</sup> For more information, see the <a href="https://github.com/rabbitmq/rabbitmq-server/releases/tag/v3.9.27">v3.9.27</a> GitHub documentation.
