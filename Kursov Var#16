# FnzAlgoritmsAndC- Kurs 
using System;
using System.Data;
using System.Data.SqlClient;
using System.Windows.Forms;

namespace Skripkin
{
    public partial class Form1 : Form
    {
        SqlConnection sqlConnection;
        string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=D:\Skipkin\Skripkin\Skripkin\Film.mdf;Integrated Security=True";

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // TODO: This line of code loads data into the 'filmDataSet1.Table' table. You can move, or remove it, as needed.
            this.tableTableAdapter.Fill(this.filmDataSet1.Table);

        }
        private async void btnUpdate_Click(object sender, EventArgs e)
        {
            if (!string.IsNullOrEmpty(txbName.Text) && !string.IsNullOrWhiteSpace(txbName.Text) && !string.IsNullOrEmpty(txbActor.Text) && !string.IsNullOrWhiteSpace(txbActor.Text)
               && !string.IsNullOrEmpty(txbDirector.Text) && !string.IsNullOrWhiteSpace(txbDirector.Text) && !string.IsNullOrEmpty(txbRating.Text) && !string.IsNullOrWhiteSpace(txbRating.Text)
               && !string.IsNullOrEmpty(txbViewer.Text) && !string.IsNullOrWhiteSpace(txbViewer.Text) && !string.IsNullOrEmpty(txbYear.Text) && !string.IsNullOrWhiteSpace(txbYear.Text) &&
                  !string.IsNullOrEmpty(txbId.Text) && !string.IsNullOrWhiteSpace(txbId.Text))
            {
                SqlConnection sqlConnection;
                sqlConnection = new SqlConnection(connectionString);
                await sqlConnection.OpenAsync();

                SqlCommand command = new SqlCommand("UPDATE [Table] SET [FilmName] = @FilmName, [SurnameActor] = @SurnameActor, [Director] = @Director, [Year] = @Year, [Rating] = @Rating, [Viewers] = @Viewers WHERE  [Id] = @Id", sqlConnection);
                command.Parameters.AddWithValue("Id", txbId.Text);
                txbId.Clear();
                command.Parameters.AddWithValue("FilmName", txbName.Text);
                txbName.Clear();
                command.Parameters.AddWithValue("Director", txbDirector.Text);
                txbDirector.Clear();
                command.Parameters.AddWithValue("SurnameActor", txbName.Text);
                txbActor.Clear();
                command.Parameters.AddWithValue("Year", txbYear.Text);
                txbYear.Clear();
                command.Parameters.AddWithValue("Rating", txbName.Text);
                txbRating.Clear();
                command.Parameters.AddWithValue("Viewers", txbName.Text);
                txbViewer.Clear();
                await command.ExecuteNonQueryAsync();

                MessageBox.Show("Данные изменены", "Данные изменены", MessageBoxButtons.OK, MessageBoxIcon.Information);
            }
            else
            {
                MessageBox.Show("Заполните все данные", "Ошибка ввода", MessageBoxButtons.OK, MessageBoxIcon.Error);
            }

        }

        private async void btnAdd_Click(object sender, EventArgs e)
        {
            if (!string.IsNullOrEmpty(txbName.Text) && !string.IsNullOrWhiteSpace(txbName.Text) && !string.IsNullOrEmpty(txbActor.Text) && !string.IsNullOrWhiteSpace(txbActor.Text)
                && !string.IsNullOrEmpty(txbDirector.Text) && !string.IsNullOrWhiteSpace(txbDirector.Text) && !string.IsNullOrEmpty(txbRating.Text) && !string.IsNullOrWhiteSpace(txbRating.Text)
                && !string.IsNullOrEmpty(txbViewer.Text) && !string.IsNullOrWhiteSpace(txbViewer.Text) && !string.IsNullOrEmpty(txbYear.Text) && !string.IsNullOrWhiteSpace(txbYear.Text))
            {
                sqlConnection = new SqlConnection(connectionString);
                await sqlConnection.OpenAsync();
                SqlCommand command = new SqlCommand("INSERT INTO [Table] (FilmName, Director, SurnameActor, Year, Rating, Viewers)VALUES(@FilmName, @Director, @SurnameActor, @Year, @Rating, @Viewers)", sqlConnection);
command.Parameters.AddWithValue("FilmName", txbName.Text);
                txbName.Clear();
                command.Parameters.AddWithValue("Director", txbDirector.Text);
                txbDirector.Clear();
                command.Parameters.AddWithValue("SurnameActor", txbName.Text);
                txbActor.Clear();
                command.Parameters.AddWithValue("Year", txbYear.Text);
                txbYear.Clear();
                command.Parameters.AddWithValue("Rating", txbName.Text);
                txbRating.Clear();
                command.Parameters.AddWithValue("Viewers", txbName.Text);
                txbViewer.Clear();

                MessageBox.Show("Данные внесены", "Данные внесены", MessageBoxButtons.OK, MessageBoxIcon.Information);
                await command.ExecuteNonQueryAsync();

            }
            else
            {
                MessageBox.Show("Заполните все данные", "Ошибка ввода", MessageBoxButtons.OK, MessageBoxIcon.Error);
            }



        }

        private async void btnDelete_Click(object sender, EventArgs e)
        {
            if (!string.IsNullOrEmpty(txbId.Text) && !string.IsNullOrWhiteSpace(txbId.Text))
            {
                SqlConnection sqlConnection;
                sqlConnection = new SqlConnection(connectionString);
                await sqlConnection.OpenAsync();
                SqlCommand command = new SqlCommand("DELETE FROM [Table] WHERE [Id] = @Id", sqlConnection);

                MessageBox.Show("Данные были удалены", "Внимание", MessageBoxButtons.OK, MessageBoxIcon.Information);
                command.Parameters.AddWithValue("Id", txbId.Text);
                txbId.Clear();

                await command.ExecuteNonQueryAsync();
            }
            else
            {
                MessageBox.Show("Заполните все данные", "Ошибка ввода", MessageBoxButtons.OK, MessageBoxIcon.Error);

            }

        }
    }
}
