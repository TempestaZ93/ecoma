<script>
  import { _ } from '../../services/i18n';
  import { Link } from "svelte-routing";
  import TopAppBar, {Row, Section, Title} from '@smui/top-app-bar'
  import IconButton from '@smui/icon-button';
  import Checkbox from '@smui/checkbox';
  import FormField from '@smui/form-field';
</script>

<nav>
 <TopAppBar
      variant="static prominent"
      color="primary"
    >
      <Row>
        <Section>
          <IconButton class="material-icons">menu</IconButton>
          <Title>Flex Static</Title>
        </Section>
        <Section align="end" toolbar>
          <IconButton class="material-icons" aria-label="Download"
            >file_download</IconButton
          >
          <IconButton class="material-icons" aria-label="Print this page"
            >print</IconButton
          >
          <IconButton class="material-icons" aria-label="Bookmark this page"
            >bookmark</IconButton
          >
        </Section>
      </Row>
    </TopAppBar>
</nav>
