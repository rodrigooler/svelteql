<script>
  import ApolloClient from "apollo-boost";
  import {
    setClient,
    getClient,
    query as SveltQuery,
    mutate as SveltMutate
  } from "svelte-apollo";

  import { GRAPHQL_URI } from "../configs/Envs";

  setClient(
    new ApolloClient({
      uri: GRAPHQL_URI
    })
  );

  export const client = getClient();
  export const query = query => SveltQuery(client, { query });
  export const mutate = (mutate, variables) =>
	SveltMutate(client, { mutate, variables });
	
	
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<h1>Hello {name}!</h1>
