<!-- SPDX-License-Identifier: 0BSD -->

# Text embeddings via OpenAI - basic Python examples

These are some examples of embeddings using OpenAI models.

Examples are here because I find each to be of some interest, but this is not
intended as a tutorial for how to use embeddings.

For instructive examples, see the official OpenAI repository
[**openai-cookbook**](https://github.com/openai/openai-cookbook).

## License

[0BSD](https://spdx.org/licenses/0BSD.html). See [**`LICENSE`**](LICENSE).

## Contents

*Summary forthcoming.* For now, look at the descriptions at the top of each
notebook.

## Notes

The examples are written to assume your API key is in a file called `.api_key`.
Do not commit it to Git! The `.gitignore` file excludes it, to help avoid that.

## Matrix multiplication

One interesting technique shown here is storing the embeddings as rows of a
matrix, then finding similarities with matrix multiplication.

The second operand can be an embedding, in which case we are multiplying a
matrix by a column vector, which is the same as taking the dot products of all
of the matrix's rows with the vector (to make the new coordinates of the
resulting vector).

If the second operand is a matrix whose *columns* are embeddings, then each
*(i, j)* entry of the resulting matrix is the dot product of the *i*th row of
the first matrix by the *j*th row of the second matrix, i.e., the similarities
of those embeddings.

The dot products are the cosine similarities with OpenAI embeddings, and with
embeddings from some other non-OpenAI models (but not all), because many
embedding models, including all OpenAI models, produce embeddings that are
already normalized (length 1).
